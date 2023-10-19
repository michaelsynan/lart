<template>
  <div class="fixed bottom-0 left-1/2 transform -translate-x-1/2 mb-10">
    <div class="flex space-x-6 justify-center items-center p-4">
      <NuxtLink to="/shop" class="bg-amber-600 px-4 py-3 text-2xl font-bold relative group top-0 hover:-top-0.5 transition-all duration-300 ease-in-out">
  <span class="text-white z-10 relative">Shop</span>
  <div class="absolute bottom-0 left-0 w-full h-full bg-teal-500 opacity-0 group-hover:opacity-100 z-[-1] transition-all duration-300 ease-in-out group-hover:bottom-[-6px] group-hover:left-[-6px]"></div>
</NuxtLink>

      <NuxtLink to="/about" class="bg-amber-600 px-4 py-3 text-2xl font-bold relative group top-0 hover:-top-0.5 transition-all duration-300 ease-in-out">
        <span class="text-white z-10 relative">About</span>
        <div class="absolute bottom-0 left-0 w-full h-full bg-teal-500 opacity-0 group-hover:opacity-100 z-[-1] transition-all duration-300 ease-in-out group-hover:bottom-[-6px] group-hover:left-[-6px]"></div>
      </NuxtLink>
      <NuxtLink to="/contact" class="bg-amber-600 px-4 py-3 text-2xl font-bold relative group top-0 hover:-top-0.5 transition-all duration-300 ease-in-out">
        <span class="text-white z-10 relative">Contact</span>
        <div class="absolute bottom-0 left-0 w-full h-full bg-teal-500 opacity-0 group-hover:opacity-100 z-[-1] transition-all duration-300 ease-in-out group-hover:bottom-[-6px] group-hover:left-[-6px]"></div>
      </NuxtLink>
    </div>
  </div>
</template>
