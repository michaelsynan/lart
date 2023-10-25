<script lang="ts" setup>
import { ref } from 'vue';
definePageMeta({
  layout: 'default'
})

const loading = ref(false);

const handleButtonClick = () => {
  loading.value = true;
  setTimeout(() => {
    loading.value = false;
  }, 2000);
};
</script>

<template>
  <div class="w-full flex justify-center">
    <div class="relative flex flex-col items-center justify-start md:mt-0 mt-20 md:justify-center h-screen w-full">
      <section class="align-left w-full mb-0 md:mb-10">
        <div class="mx-auto w-full md:w-xl px-4">
          <h2
            class="mb-4 text-5xl md:text-5xl tracking-tight font-extrabold text-left md:text-center text-white px-0 pb-3 md:px-4">
            Get In Touch</h2>
          <form action="#" class="space-y-6 text-lg">
            <div>
              <label for="email" class="block mb-2 text-gray-200 text-left font-bold">Email</label>
              <input type="email" id="email"
                class="text-base shadow-sm bg-gray-50 border border-gray-300 text-gray-900  rounded-sm focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light"
                placeholder="your@email.com" required>
            </div>
            <div>
              <label for="subject" class="block mb-2  font-bold text-gray-200 text-left">Subject</label>
              <input type="text" id="subject"
                class="text-base block p-3 w-full text-gray-900 bg-gray-50 rounded-sm border border-gray-300 shadow-sm focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light"
                placeholder="Let us know how we can help you" required>
            </div>
            <div class="sm:col-span-2">
              <label for="message" class="block mb-2 font-bold text-gray-200 text-left">Message</label>
              <textarea id="message" rows="6"
                class="text-base block p-2.5 w-full text-gray-900 bg-gray-50 rounded-sm shadow-sm border border-gray-300 focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                placeholder="Send a detailed message..."></textarea>
            </div>
            <button type="submit" 
        @click="handleButtonClick"
        class="uppercase tracking-wide flex justify-center items-center w-full h-12 text-xl font-bold text-center text-white rounded-sm  focus:ring-4 focus:outline-none focus:ring-primary-300 bg-teal hover:bg-teal-500 transition-color duration-100 ease-in-out dark:focus:ring-primary-800">
  
  <span v-if="!loading" class="w-full text-center">Send</span>

  <div v-if="loading" class="flex items-center justify-center">
    <svg xmlns="http://www.w3.org/2000/svg" 
         class="animate-spin h-6 w-6" 
         viewBox="0 0 24 24" 
         style="transform-origin: center;">
      <path fill="white" d="M12 4V2A10 10 0 0 0 2 12h2a8 8 0 0 1 8-8Z" />
    </svg>
  </div>
  
</button>

          </form>
        </div>
      </section>
    </div>
  </div>
</template>

<style scoped>
.animate-spin {
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }

  100% {
    transform: rotate(360deg);
  }
}
</style>  