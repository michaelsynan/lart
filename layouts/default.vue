<template>
  <main class="text-center relative">
    <div class="absolute inset-0 bg-black opacity-75 backdrop-blur-md"></div>
    <div class="relative">
      <MainHeading />
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
