<template>
  <main class="text-center relative !bg-amber-950">
    <div class="fixed h-full w-20 z-100 bg-gradient-to-r-custom"></div>
    <div class="fixed h-full w-20 z-100 right-0 bg-gradient-to-l-custom"></div>
    <div class="absolute inset-0 bg-black opacity-75 backdrop-blur-md"></div>
    <div class="relative">
      <slot />
      <BottomNav />
    </div>
  </main>
</template>

<style>
  .bg-gradient-to-r-custom {
    background-image: linear-gradient(to right, #110600, transparent);
  }

  .bg-gradient-to-l-custom {
    background-image: linear-gradient(to left, #110600, transparent);
  }
</style>
