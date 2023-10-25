<script setup lang="ts">
import { ref, onMounted } from 'vue';
const { delay = 0 } = defineProps(['delay']);
const online = useOnline(); // Assuming useOnline is imported or defined
const showWords = ref([false, false, false, false]);

definePageMeta({
  layout: 'home'
})

onMounted(() => {
  setTimeout(() => { showWords.value[0] = true; }, delay + 1000);
  setTimeout(() => { showWords.value[1] = true; }, delay + 1500);
  setTimeout(() => { showWords.value[2] = true; }, delay + 2000);
  setTimeout(() => { showWords.value[3] = true; }, delay + 2500);
});
</script>
<template>
  <div class="relative flex flex-col w-full h-screen">
    <!-- Mobile only -->
    <div id="headingmobile" class="md:hidden top-0 fixed left-1/2 transform -translate-x-1/2 text-5xl font-bold mt-4 z-100 w-full mainheading">
      <span>L'art de la rue</span>
    </div>
    <!-- Desktop only -->
    <div id="headingdesktop" class="hidden md:flex md:absolute md:inset-0 items-center justify-center">
      <div class="text-center text-white mb-20 grid grid-cols-2 md:flex md:flex-row"
        style="font-size: clamp(16px, 14vw, 240px);">
        <div v-if="showWords[0]"
          class="z-100 pr-8 md:pr-20 pointer-events-none text-outline mainheading -rotate-15 text-stone-100 ">
          L'art</div>
        <div v-if="showWords[1]" class="pr-8 md:pr-20 text-outline mainheading -rotate-15 text-stone-100 ">de
        </div>
        <div v-if="showWords[2]"
          class="z-100 pr-8 md:pr-20 pointer-events-none text-outline mainheading -rotate-15 text-stone-100">
          la</div>
        <div v-if="showWords[3]" class="text-outline mainheading -rotate-15 text-stone-100 ">rue</div>
      </div>
    </div>
    <MainRow :speed="2" />
    <MainRow :delay="1000" :speed="3" />
    <MainRow :delay="2000" :speed="2" />
  </div>
</template>



<style block>
.text-outline {}
</style>