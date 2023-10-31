<script lang="ts" setup>
import { ref } from 'vue';

const loading = ref(false);
const response = ref('');
const formSent = ref(false); // New variable to track if form is sent successfully

const handleButtonClick = () => {
  if (formSent.value) return; // Prevent resending if form already sent

  loading.value = true;

  // Simulating a network call to send the email
  setTimeout(() => {
    loading.value = false;

    // Assuming success for now; later, you'd check the result of your actual mailer function.
    const isSuccess = true; // replace with actual success condition

    if (isSuccess) {
      response.value = 'Success! Thank you for your message.';
      formSent.value = true; // Set formSent to true on success
    } else {
      response.value = 'Something went wrong. Please try again later.';
    }
  }, 2000);
};
</script>


<template>
  <div class="w-full flex justify-center overflow-y-hidden">
    <div class="relative flex flex-col items-center justify-start md:mt-40 mt-28 h-full w-full">
      <section class="align-left w-full mb-0 md:mb-10">
        <div class="mx-auto w-full md:w-lg px-4">
          <h2
            class="mb-4 text-2xl md:text-3xl tracking-tight font-extrabold text-center md:text-center text-white px-0 pb-3 md:px-4 mainheading">
            Get In Touch</h2>
          <form action="#" class="space-y-6 text-base">
            <div>
              <label for="email" class="block mb-1 text-gray-200 text-left font-bold">Email</label>
              <input type="email" id="email"
                class="text-sm shadow-sm bg-gray-50 border border-gray-300 text-gray-900  rounded-sm focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light"
                placeholder="your@email.com" required>
            </div>
            <div>
              <label for="subject" class="block mb-1  font-bold text-gray-200 text-left">Subject</label>
              <input type="text" id="subject"
                class="text-sm block p-3 w-full text-gray-900 bg-gray-50 rounded-sm border border-gray-300 shadow-sm focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500 dark:shadow-sm-light"
                placeholder="What can we help you with?" required>
            </div>
            <div class="sm:col-span-2">
              <label for="message" class="block mb-1 font-bold text-gray-200 text-left">Message</label>
              <textarea id="message" rows="6"
                class="text-sm block p-2.5 w-full text-gray-900 bg-gray-50 rounded-sm shadow-sm border border-gray-300 focus:ring-primary-500 focus:border-primary-500 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-primary-500 dark:focus:border-primary-500"
                placeholder="Write a nice message..."></textarea>
            </div>
            <button type="submit" @click="handleButtonClick" :disabled="formSent" :class="{
              'cursor-not-allowed !bg-stone-500 !text-stone-300': formSent,
              'hover:bg-teal-500': !formSent
            }"
              class="uppercase tracking-wide flex justify-center items-center w-full h-10 md:h-12 text-lg md:text-xl font-bold text-center text-white rounded-sm focus:ring-4 focus:outline-none focus:ring-primary-300 bg-teal transition-color duration-100 ease-in-out dark:focus:ring-primary-800">

              <span v-if="!loading" class="w-full text-center">Send</span>
              <div v-if="loading" class="flex items-center justify-center">
                <svg xmlns="http://www.w3.org/2000/svg" class="animate-spin h-6 w-6" viewBox="0 0 24 24"
                  style="transform-origin: center;">
                  <path fill="white" d="M12 4V2A10 10 0 0 0 2 12h2a8 8 0 0 1 8-8Z" />
                </svg>
              </div>
            </button>
            <div class="h-6">
              <div v-if="response" class="">{{ response }}</div>
            </div>
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