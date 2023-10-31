<template>
  <main class="text-center relative">
    <div class="absolute inset-0 bg-black opacity-75 backdrop-blur-md h-screen "></div>
    <div class="bg-title absolute inset-0 z-[-1] flex flex-wrap h-screen overflow-y-hidden">
      <div v-for="i in 100" :key="i" class="text-wrapper"></div>
    </div>
    <div class="relative">
      <!-- <MainHeading /> -->
      <slot />
      <BottomNav />
    </div>
  </main>
</template>

<style>
  .bg-title {
    flex-wrap: wrap;
    justify-content: center; /* Horizontally center */
    align-items: center;      /* Vertically center */
  }

  .text-wrapper::before {
    content: "L'ART DE LA RUE";
    position: relative;
    z-index: -1;
    font-size: clamp(3rem, 6vw, 6rem); /* Extra small screens */
    line-height: 1;
    color: rgba(255, 255, 255, 0.25);
    pointer-events: none;
    white-space: nowrap;
    font-family: 'Dortmund', sans-serif;
    font-weight: 800;
  }

  /* Small screens */
  @media screen and (min-width: 480px) {
    .text-wrapper::before {
      font-size: clamp(4rem, 8vw, 8rem);
    }
  }

  /* Between Small and Medium screens */
  @media screen and (min-width: 640px) {
    .text-wrapper::before {
      font-size: clamp(6rem, 9vw, 10rem);
    }
  }

  /* Medium screens */
  @media screen and (min-width: 768px) {
    .text-wrapper::before {
      font-size: clamp(8rem, 10vw, 12rem);
    }
  }

  /* Between Medium and Large screens */
  @media screen and (min-width: 900px) {
    .text-wrapper::before {
      font-size: clamp(9rem, 11vw, 14rem);
    }
  }

  /* Large screens */
  @media screen and (min-width: 1024px) {
    .text-wrapper::before {
      font-size: clamp(10rem, 12vw, 16rem);
    }
  }
</style>


