<template>
  <div class="fixed bottom-0 left-1/2 transform -translate-x-1/2 mb-10">
    <div class="flex space-x-3 md:space-x-6 justify-center items-center p-2 md:p-4">
      <NuxtLink to="/"
        class="rounded-sm bg-amber-600 px-3 md:px-4 py-2 md:py-3 text-xl md:text-2xl font-bold relative group top-0 hover:-top-0.5 transition-all duration-200 ease-in-out">
        <span class="text-white z-10 relative">Home</span>
        <div
          class="rounded-sm absolute bottom-0 left-0 w-full h-full bg-teal-500 opacity-0 group-hover:opacity-100 z-[-1] transition-all duration-200 ease-in-out group-hover:bottom-[-4px] group-hover:left-[-4px]">
        </div>
      </NuxtLink>
      <NuxtLink to="/about"
        class="rounded-sm bg-amber-600 px-3 md:px-4 py-2 md:py-3 text-xl md:text-2xl font-bold relative group top-0 hover:-top-0.5 transition-all duration-200 ease-in-out">
        <span class="text-white z-10 relative">About</span>
        <div
          class="rounded-sm absolute bottom-0 left-0 w-full h-full bg-teal-500 opacity-0 group-hover:opacity-100 z-[-1] transition-all duration-200 ease-in-out group-hover:bottom-[-4px] group-hover:left-[-4px]">
        </div>
      </NuxtLink>
      <NuxtLink to="/contact"
        class="rounded-sm bg-amber-600 px-3 md:px-4 py-2 md:py-3 text-xl md:text-2xl font-bold relative group top-0 hover:-top-0.5 transition-all duration-200 ease-in-out">
        <span class="text-white z-10 relative">Contact</span>
        <div
          class="rounded-sm absolute bottom-0 left-0 w-full h-full bg-teal-500 opacity-0 group-hover:opacity-100 z-[-1] transition-all duration-200 ease-in-out group-hover:bottom-[-4px] group-hover:left-[-4px]">
        </div>
      </NuxtLink>
      <NuxtLink to="/shop"
        class="rounded-sm bg-amber-600 px-3 md:px-4 py-2 md:py-3 text-xl md:text-2xl font-bold relative group top-0 hover:-top-0.5 transition-all duration-200 ease-in-out">
        <span class="text-white z-10 relative">Shop</span>
        <div
          class="rounded-sm absolute bottom-0 left-0 w-full h-full bg-teal-500 opacity-0 group-hover:opacity-100 z-[-1] transition-all duration-200 ease-in-out group-hover:bottom-[-4px] group-hover:left-[-4px]">
        </div>
      </NuxtLink>
  </div>
</div></template>
