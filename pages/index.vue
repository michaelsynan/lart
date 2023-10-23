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
    <div class="absolute inset-0 flex items-center justify-center">
      <div class="text-center text-white mb-20 grid grid-cols-2 md:flex md:flex-row"
        style="font-size: clamp(16px, 14vw, 240px);">
        <div v-if="showWords[0]"
          class="z-100 pr-8 md:pr-20 pointer-events-none text-outline mainheading -rotate-15 text-stone-200 ">
          L'art</div>
        <div v-if="showWords[1]" class="pr-8 md:pr-20text-outline mainheading -rotate-15 text-stone-200 ">de
        </div>
        <div v-if="showWords[2]"
          class="z-100 pr-8 md:pr-20 pointer-events-none text-outline mainheading -rotate-15 text-stone-200">
          la</div>
        <div v-if="showWords[3]" class="text-outline mainheading -rotate-15 text-stone-200 ">rue</div>
      </div>



    </div>
    <MainRow class="w-full" :speed="2" />
    <MainRow class="w-full" :delay="1000" :speed="3" />
    <MainRow class="w-full" :delay="2000" :speed="2" />
  </div>
</template>


<style block>
.text-outline {}

</style>