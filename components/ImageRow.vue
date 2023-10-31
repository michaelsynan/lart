<script setup lang="ts">
import { onMounted, ref, nextTick, defineProps } from 'vue';

const { speed } = defineProps<{ speed: number }>();

const imageList = ['1.jpg', '2.jpg', '3.jpg', '4.jpg', '5.jpg', '6.jpg', '7.jpg', '8.jpg', '9.jpg', '10.jpg', '11.jpg', '12.jpg', '13.jpg', '14.jpg', '15.jpg', '16.jpg', '17.jpg', '18.jpg', '19.jpg', '20.jpg', '21.jpg', '22.jpg', '23.jpg', '24.jpg', '25.jpg'];
const imageContainer = ref(null);
let imageCounter = 0;
let interval;
let primaryPosition = 0; // Moved outside of startScrolling

function getRandomImageSrc() {
  const index = Math.floor(Math.random() * imageList.length);
  return imageList[index];
}

function pauseScrolling() {
  clearInterval(interval);
}

function resumeScrolling() {
  startScrolling();
}

function startScrolling() {
  interval = setInterval(() => {
    const spacing = 500;
  
    primaryPosition++;
  
    Array.from(imageContainer.value.children).forEach((img: HTMLImageElement) => {
      let imgPosition = parseInt(img.style.left, 10);
      imgPosition++;
      img.style.left = `${imgPosition}px`;
    });
  
    if (primaryPosition % spacing === 0) {
      createImage(0);
    }
  }, 10 / speed);
}

const createImage = (position) => {
  const img = document.createElement('img');
  img.src = getRandomImageSrc();
  img.className = 'w-48 h-48 object-cover';
  img.style.position = 'absolute';
  img.style.left = `${position}px`;

  if (imageCounter % 2 !== 0) {
    img.style.top = '20px';
  }

  img.addEventListener('mouseover', pauseScrolling);
  img.addEventListener('mouseout', resumeScrolling);

  imageContainer.value.appendChild(img);
  imageCounter++;
};

onMounted(async () => {
  await nextTick();
  const container = imageContainer.value;
  container.style.width = '4000px';
  container.style.left = '-500px';

  for (let i = 0; i < 4000; i += 500) {
    createImage(i);
  }

  startScrolling();
});
</script>

<template>
  <div ref="imageContainer" class="relative h-40 overflow-visible">
    <!-- Images will be appended here -->
  </div>
</template>

<style scoped>
  img {
    transition: transform 0.3s ease-in-out;
  }

  img:hover {
    transform: scale(1.2) !important;
  }
</style>
