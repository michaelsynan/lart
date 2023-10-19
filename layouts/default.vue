<template>
  <main class="text-center relative !bg-amber-950">
    <div class="absolute inset-0 bg-black opacity-75 backdrop-blur-md"></div>
    <div class="relative">
      <slot />
      <BottomNav />
    </div>
  </main>
</template>

<style>
main {
  background-color: black;
}
</style>
