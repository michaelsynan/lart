<script lang="ts" setup>
definePageMeta({
  layout: 'default'
})
</script>

<template>
   <div class="w-full flex justify-center">
  <div class="relative flex flex-col items-center justify-center h-screen w-full">
<section class="align-left w-full">
  <div class="mx-auto w-full md:w-2xl px-4">
      <h2 class="mb-4 text-6xl tracking-tight font-extrabold text-center text-white px-4">Get In Touch</h2>
      <form action="#" class="space-y-8 text-lg">
          <div>
              <label for="email" class="block mb-2 ttext-gray-300 text-left font-bold">Email</label>
              <input type="email" id="email" class="shadow-sm bg-gray-50 border border-gray-300 text-gray-900  rounded-sm focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light" placeholder="your@email.com" required>
          </div>
          <div>
              <label for="subject" class="block mb-2  font-bold text-gray-300 text-left">Subject</label>
              <input type="text" id="subject" class="block p-3 w-full text-gray-900 bg-gray-50 rounded-sm border border-gray-300 shadow-sm focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light" placeholder="Let us know how we can help you" required>
          </div>
          <div class="sm:col-span-2">
              <label for="message" class="block mb-2 font-bold text-gray-400 text-left">Message</label>
              <textarea id="message" rows="6" class="block p-2.5 w-full text-gray-900 bg-gray-50 rounded-sm shadow-sm border border-gray-300 focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500" placeholder="Send a detailed message..."></textarea>
          </div>
          <button type="submit" class="uppercase tracking-wide inline-flex justify-between w-full py-3 px-5 text-2xl font-bold text-center text-white rounded-sm bg-primary-700  hover:bg-primary-800 focus:ring-4 focus:outline-none focus:ring-primary-300 bg-teal dark:focus:ring-primary-800"><div class="w-full">Send</div>
            </button>
      </form>
  </div>
</section>
    </div>
    </div>
</template>

<style scoped></style>
