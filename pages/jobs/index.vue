<template>
    <div>
    <div class="relative h-[200px] shadow-lg overflow-hidden">
        <img src="assets/img/bgjob.jpg" alt="Jobs Header Image" class="w-full h-full object-cover" />
        <div class="absolute inset-0 bg-black/60" />
        <div class="absolute inset-0 flex flex-col items-center justify-center gap-4">
            <h1 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white" data-aos="fade-down"
                data-aos-duration="800">
                Let's find your!
            </h1>
            <nav class="flex items-center gap-2 text-sm md:text-base text-white/90" data-aos="fade-up"
                data-aos-duration="800" data-aos-delay="200">
                <nuxt-link to="/" class="hover:text-sky-400 transition-colors">
                    Home
                </nuxt-link>
                <span class="text-white/60">/</span>
                <span class="text-sky-400">Jobs</span>
            </nav>
        </div>
    </div>

    <div class="bg-white py-8">
        <div class="max-w-4xl mx-auto px-4">
            <div class="flex flex-col md:flex-row gap-4">
                <div class="flex-1">
                    <input type="text" placeholder="Your dream job?"
                        class="w-full px-4 py-3 rounded-xl border border-gray-800 focus:border-sky-500 focus:ring-1 focus:ring-sky-500 outline-none transition-all" />
                </div>
                <div class="flex-1">
                    <select
                        class="w-full px-4 py-3 rounded-xl border border-gray-800 focus:border-sky-500 focus:ring-1 focus:ring-sky-500 outline-none transition-all">
                        <option value="">All Categories</option>
                        <option value="fulltime">Full Time</option>
                        <option value="parttime">Part Time</option>
                        <option value="freelance">Freelance</option>
                    </select>
                </div>
                <button class="px-6 py-3 bg-sky-600 text-white rounded-lg hover:bg-sky-700 transition-all">
                    Search
                </button>
            </div>
        </div>
    </div>

    <div class="bg-sky-700 py-10">
        <Jobs />
    </div>
    </div>
</template>