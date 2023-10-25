<script setup lang="ts">
definePageMeta({
  layout: 'default'
})
</script>

<template>
  <div class="w-full flex justify-center px-4 overflow-y-hidden">
    <div class="relative flex flex-col items-center justify-start  mt-28 md:mt-40 h-full">
      <div class="rounded-md w-content mb-12">
        <!-- <MainHeading /> -->
        <h2 class="text-lg md:text-xl font-bold py-2 uppercase rounded" bakclass="bg-teal">
          <span class="mainheading py-2">Established 2000</span>
        </h2>
      </div>

      <p class="px-2 text-lg md:text-xl max-w-lg leading-loose mb-6 serif tracking-wide">NYC-based street artist Mohammad
        designs jewelry that brings to life the history and culture of the city in which he lives. Follow his <a
          href="https://www.instagram.com/ojo_dolce/?hl=en"
          class="border-b-2 hover:border-b-3 hover:border-teal">Instagram</a> for the latest updates.</p>
      <p class="px-2 text-lg md:text-xl max-w-lg leading-loose mb-20 serif tracking-wide">For custom pieces or press
        inquiries, please send a message <NuxtLink to="/contact" class="border-b-2 hover:border-b-3 hover:border-teal">
          here</NuxtLink>.</p>
      <p class="px-2 text-base md:text-lg max-w-lg leading-loose mb-10 text-stone-700">Website by <a
          href="https://formworkstudios.com" class="hover:border-b-2 hover:border-stone-700">Formwork Studios</a></p>

    </div>
  </div>
</template>

<style scoped></style>
