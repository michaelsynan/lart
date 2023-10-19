<script setup lang="ts">
import { defineProps } from 'vue';
const { delay = 0 } = defineProps(['delay']);
const online = useOnline(); // Assuming useOnline is imported or defined
</script>

<template>
  <div class="relative flex flex-col w-full h-screen">
    <div class="absolute inset-0 flex items-center justify-center">
      <div class="text-center text-white mb-20 flex flex-row" style="font-size: clamp(16px, 14vw, 240px);">
  <div id="L_art" class="z-100 pr-20 pointer-events-none text-outline mainheading -rotate-15 text-stone-300">L'art</div>
  <div id="de" class="pr-20 text-outline mainheading -rotate-15 text-stone-300">de</div>
  <div id="la" class="z-100 pr-20 pointer-events-none text-outline mainheading -rotate-15 text-stone-300">la</div>
  <div id="rue" class="text-outline mainheading -rotate-15 text-stone-300">rue</div>
</div>


    </div>
    <MainRow class="w-full" :speed="2"/>
    <MainRow class="w-full" :delay="1000" :speed="3"/>
    <MainRow class="w-full" :delay="2000" :speed="2" />
  </div>
</template>


<style block>
.text-outline {

}

</style>