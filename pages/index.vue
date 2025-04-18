<template>
  <div class="relative w-full">
    <img src="assets/img/bg.jpg" alt="Background Image" class="w-full h-auto object-cover md:h-[500px] lg:h-[600px]">
    <div class="absolute inset-0 me-4 sm:me-20 md:me-40 lg:me-60 flex items-center justify-end">
      <div class="text-justify p-4 max-w-[280px] sm:max-w-sm md:max-w-md">
        <h1 class="text-2xl sm:text-3xl md:text-4xl font-bold text-sky-700" data-aos="fade-up" data-aos-duration="1000">
          Let's find your purpose
        </h1>
        <p class="mt-2 text-sm sm:text-base md:text-lg text-black break-words" data-aos="fade-up"
          data-aos-duration="2000">
          Astacode is a company engaged in the technology sector,
          with our motto being Support Your System.
        </p>
        <nuxt-link to="/jobs"
          class="mt-4 inline-block px-4 sm:px-5 md:px-6 py-2 sm:py-3 bg-blue-600 text-white text-sm sm:text-base rounded-lg hover:bg-blue-700"
          data-aos="fade-up" data-aos-duration="3000">
          Explore Jobs
        </nuxt-link>
      </div>
    </div>
  </div>

  <Life />
  <div class="bg-sky-700 mt-8 sm:mt-12 md:mt-16 py-10">
    <h1 class="text-2xl sm:text-3xl md:text-4xl font-semibold text-white text-center">
      So, are you ready to grow beyond with us?
    </h1>


    <Jobs :limit="3" />


    <div class="flex justify-center mt-8">

      <nuxt-link to="/jobs" class="flex items-center gap-2 px-6 py-3 text-white border border-white/20 rounded-lg hover:bg-sky-500
                transition-all duration-300">
        See More
        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
        </svg>
      </nuxt-link>
    </div>
  </div>
</template>
