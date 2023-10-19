<script setup>
import { ref, onMounted, defineProps } from 'vue';
const router = useRouter()

const { delay = 0, speed = 1 } = defineProps(['delay', 'speed']); // Added speed prop
const boxRefs = Array(4).fill(null).map(() => ref(null));
const images = Array.from({ length: 12 }, (_, i) => `${i + 1}.jpg`);

function getRandomImage() {
  return images[Math.floor(Math.random() * images.length)];
}

function getRandomPositionFactor() {
  const factors = [0.23, 0.24, 0.25, 0.26, 0.27];
  return factors[Math.floor(Math.random() * factors.length)];
}

onMounted(() => {
  setTimeout(() => {
    const step = speed; // Use the speed prop
    function animateBox(box, startPosition) {
      let position = startPosition;
      function moveBox() {
        if (position <= -200) {
          position = window.innerWidth + 200;
        }
        position -= step;
        box.style.right = `${position}px`;
        requestAnimationFrame(moveBox);
      }
      box.style.right = `${position}px`;
      requestAnimationFrame(moveBox);
    }

    boxRefs.forEach((boxRef, index) => {
      const initialPosition = window.innerWidth + 200 + (index * window.innerWidth * getRandomPositionFactor());
      boxRef.value.style.backgroundImage = `url(${getRandomImage()})`;
      animateBox(boxRef.value, initialPosition);
    });
  }, delay);
});

// router.beforeEach((to, from, next) => {
//  console.log('turtles delay');
//  animationIsComplete = true;
//  if (animationIsComplete) {
//    next();
//  } else {
    // delay the navigation or trigger the animation to complete
//  }
// });


</script>

<template>
  <div class="flex justify-center items-center h-full">
    <div 
      v-for="(_, index) in boxRefs"
      :key="index"
      :ref="el => { boxRefs[index].value = el }"
      class="fixed w-25 h-25 opacity-100 scale-on-hover"
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
  transition: transform 0.3s ease-in-out;
}
.scale-on-hover:hover {
  transform: scale(1.5);
}
</style>
