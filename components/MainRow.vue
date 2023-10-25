<script setup>
import { ref, reactive, onMounted } from 'vue';

const { speed = 1 } = defineProps(['speed']);
const boxRefs = Array(4).fill(null).map(() => ref(null));
const state = reactive({ step: speed, isHovered: false });
const images = Array.from({ length: 14 }, (_, i) => `${i + 1}.jpg`);

function getRandomImage() {
  return images[Math.floor(Math.random() * images.length)];
}

function shuffleArray(array) {
  for (let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];
  }
}

let interval;
function easeStep(target) {
  clearInterval(interval);
  interval = setInterval(() => {
    if (Math.abs(state.step - target) < 0.01) {
      clearInterval(interval);
      state.step = target;
    } else {
      state.step += (target - state.step) * 0.1;
    }
  }, 16);
}

function calculateSpacingMultiplier(windowWidth) {
  if (windowWidth < 800) {
    return 1;
  }
  return 0.3;
}

onMounted(() => {
  function animateBox(box) {
    let position = parseFloat(box.style.right);
    function moveBox() {
      if (position <= -220) {
        position = Math.max(window.innerWidth, lastRight + 200);
        lastRight = position + 220;
      }
      position -= state.step;
      box.style.right = `${position}px`;
      requestAnimationFrame(moveBox);
    }
    requestAnimationFrame(moveBox);
  }

  shuffleArray(images);

  const randomIndexes = [0, 1, 2, 3];
  shuffleArray(randomIndexes);

  let lastRight = 0;

  randomIndexes.forEach((index, i) => {
    const initialPosition = lastRight + 200;
    lastRight = initialPosition + 220;

    const boxRef = boxRefs[index];
    boxRef.value.style.right = `${initialPosition}px`;
    boxRef.value.style.backgroundImage = `url(${images[i]})`;
    boxRef.value.style.opacity = '0';

    setTimeout(() => {
      boxRef.value.style.transition = 'opacity .1s ease-in';
      boxRef.value.style.opacity = '1';
      animateBox(boxRef.value);
    }, i * 200);
  });
});



</script>

<template>
  <div 
    class="flex justify-center items-center h-full overflow-x-hidden"
    @mouseover="easeStep(0)"
    @mouseout="easeStep(speed)"
  >
    <div 
      v-for="(boxRef, index) in boxRefs"
      :key="index"
      :ref="el => { boxRefs[index].value = el }"
      class="fixed w-25 h-25 opacity-0 scale-on-hover rounded"
      :class="{
        'small-box': index === 0 // replace the condition with your own logic
      }"
      :style="{ 
        width: '220px', 
        height: '220px', 
        backgroundSize: 'cover',
        'margin-top': index % 2 === 0 ? '100px' : '0px' 
      }"
    >
    </div>
  </div>
</template>


<style>
.scale-on-hover {
  transition: transform 0.2s ease-in-out !important;
}
.scale-on-hover:hover {
  transform: scale(1.5) !important;
}

@media (max-width: 768px) {
  .small-box {
    @apply w-12 h-12;
  }
}



</style>
