<script setup lang="ts">
definePageMeta({
  layout: 'default'
})
</script>

<template>
  <div class="w-full flex justify-center px-4">
    <div class="relative flex flex-col items-center justify-start md:mt-0 mt-20 md:justify-center h-screen">
    <div class="border-4 border-teal mb-10 rounded-md bg-teal w-full">
    <h1 class="text-4xl md:text-6xl font-bold pb-4 px-6 md:px-10 py-4 md:py-6 tracking-wide md:tracking-wider rounded bg-stone-950 w-full mainheading">L'art de la rue</h1>
    <h2 class="text-lg md:text-xl w-full bg-teal w-full font-bold py-2 uppercase mainheading"><span class="">Established 2000</span></h2>
    </div>
    <p class="px-4 text-lg md:text-xl max-w-xl leading-loose mb-6 serif tracking-wide">NYC-based street artist Mohammad designs jewelry that brings to life the history and culture of the city in which he lives. Follow his <a href="https://www.instagram.com/ojo_dolce/?hl=en" class="border-b-2 hover:border-b-3 hover:border-teal">Instagram</a> for the latest updates.</p>
    <p class="px-4 text-lg md:text-xl max-w-xl leading-loose mb-20 serif tracking-wide">For custom pieces or press inquiries, please send a message <NuxtLink to="/contact" class="border-b-2 hover:border-b-3 hover:border-teal">here</NuxtLink>.</p>
    <p class="px-4 text-base md:text-lg max-w-xl leading-loose mb-10 text-stone-700">Website by <a href="https://formworkstudios.com" class="hover:border-b-2 hover:border-stone-700">Formwork Studios</a></p>

  </div>
  </div>
</template>

<style scoped>
</style>
