<template>
  <div class="relative w-full">
    <img src="assets/img/bg.jpg" alt="Background Image" class="w-full h-auto object-cover md:h-[500px] lg:h-[600px]">
    <div class="absolute inset-0 px-4 flex items-center sm:justify-end">
      <div class="bg-white/90 backdrop-blur-sm p-6 rounded-lg w-full max-w-[320px] sm:max-w-sm md:max-w-md 
                  sm:me-8 md:me-16 lg:me-32">
        <h1 class="text-2xl sm:text-3xl md:text-4xl font-bold text-sky-700" data-aos="fade-up" data-aos-duration="1000">
          Let's find your purpose
        </h1>
        <p class="mt-4 text-sm sm:text-base md:text-lg text-gray-800" data-aos="fade-up" data-aos-duration="2000">
          Astacode is a company engaged in the technology sector,
          with our motto being Support Your System.
        </p>
        <nuxt-link to="/jobs" class="mt-6 inline-flex items-center px-4 sm:px-5 md:px-6 py-3 bg-blue-600 text-white 
                 text-sm sm:text-base rounded-lg hover:bg-blue-700 transition-all" data-aos="fade-up"
          data-aos-duration="3000">
          Explore Jobs
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-2" fill="none" viewBox="0 0 24 24"
            stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
          </svg>
        </nuxt-link>
      </div>
    </div>
  </div>

  <Life />


  <div class="bg-sky-700 mt-6 sm:mt-12 py-8 sm:py-10 px-4">
    <h1 class="text-xl sm:text-2xl md:text-3xl lg:text-4xl font-semibold text-white text-center px-4">
      So, are you ready to grow beyond with us?
    </h1>

    <Jobs :limit="3" />

    <div class="flex justify-center mt-6 sm:mt-8">
      <nuxt-link to="/jobs" class="flex items-center gap-2 px-4 sm:px-6 py-2 sm:py-3 text-white border border-white/20 
                        rounded-lg hover:bg-sky-500 transition-all duration-300">
        See More Jobs
        <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 sm:h-5 sm:w-5" fill="none" viewBox="0 0 24 24"
          stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3" />
        </svg>
      </nuxt-link>
    </div>
  </div>
</template>