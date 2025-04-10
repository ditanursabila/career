<template>
  <header class="fixed top-0 left-0 right-0 z-50 bg-white shadow-sm">
    <nav class="max-w-[85rem] mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex h-16 items-center justify-between">
        <nuxt-link to="/" class="flex-shrink-0">
          <img src="assets/img/logo1.png" alt="Astacode Logo" class="h-10 w-auto" />
        </nuxt-link>

        <!-- Mobile menu-->
        <div class="flex md:hidden">
          <button type="button"
            class="inline-flex items-center justify-center rounded-md p-2 text-gray-700 hover:bg-gray-100 hover:text-gray-900 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-sky-500"
            @click="isOpen = !isOpen">
            <span class="sr-only">Open main menu</span>
         
            <svg class="block h-6 w-6" :class="{ 'hidden': isOpen, 'block': !isOpen }"
              xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
         
            <svg class="h-6 w-6" :class="{ 'block': isOpen, 'hidden': !isOpen }" xmlns="http://www.w3.org/2000/svg"
              fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>

        <!-- Desktop menu -->
        <div class="hidden md:flex md:items-center md:space-x-6">
          <nuxt-link to="/" class="text-base font-medium text-gray-800 hover:text-sky-500 transition-colors">
            Home
          </nuxt-link>
          <nuxt-link to="/jobs" class="text-base font-medium text-gray-800 hover:text-sky-500 transition-colors">
            Jobs
          </nuxt-link>
          <nuxt-link to="/contact" class="text-base font-medium text-gray-800 hover:text-sky-500 transition-colors">
            Contact
          </nuxt-link>
          <nuxt-link to="https://www.astacode.id/" target="_blank"
            class="ml-8 inline-flex items-center justify-center px-4 py-2 border border-transparent rounded-md shadow-sm text-base font-medium text-white bg-sky-600 hover:bg-sky-700 transition-colors">
            Astacode.id
          </nuxt-link>
        </div>
      </div>

      <!-- Mobile menu -->
      <div class="md:hidden" :class="{ 'block': isOpen, 'hidden': !isOpen }">
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <nuxt-link to="/"
            class="block px-3 py-2 rounded-md text-base font-medium text-gray-800 hover:text-sky-500 hover:bg-gray-100 transition-colors">
            Home
          </nuxt-link>
          <nuxt-link to="/jobs"
            class="block px-3 py-2 rounded-md text-base font-medium text-gray-800 hover:text-sky-500 hover:bg-gray-100 transition-colors">
            Jobs
          </nuxt-link>
          <nuxt-link to="/contact"
            class="block px-3 py-2 rounded-md text-base font-medium text-gray-800 hover:text-sky-500 hover:bg-gray-100 transition-colors">
            Contact
          </nuxt-link>
          <nuxt-link to="https://www.astacode.id/" target="_blank"
            class="block px-3 py-2 rounded-md text-base font-medium text-white bg-sky-600 hover:bg-sky-700 transition-colors">
            Astacode.id
          </nuxt-link>
        </div>
      </div>
    </nav>
  </header>

  <div class="h-16"></div>
</template>

<script setup>
import { ref } from 'vue'

const isOpen = ref(false)
</script>