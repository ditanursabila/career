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
                    <span class="text-sky-400">Detail Jobs</span>
                </nav>
            </div>
        </div>

        <div class="max-w-7xl mx-auto px-4 py-8">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <!-- Job Summary Card -->
                <div class="md:col-span-1">
                    <div class="border border-gray-800 bg-white rounded-lg p-6 shadow-sm">
                        <h2 class="text-xl font-semibold text-gray-900 mb-2">Frontend Web Developer</h2>
                        <p class="text-gray-600 text-lg mb-4">Freelance</p>
                        <div class="flex items-center gap-2 text-gray-500">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24"
                                stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
                            </svg>
                            <span>1-15 Mei</span>
                        </div>
                    </div>
                    <div class="mt-8">
                        <nuxt-link to="../jobs/form">
                            <button
                                class="w-full md:w-auto px-6 py-3 bg-sky-600 text-white rounded-lg hover:bg-sky-700 transition-all">
                                Apply Now

                            </button>
                        </nuxt-link>
                    </div>
                </div>

                <!-- Job Details Card -->
                <div class="md:col-span-2">
                    <div class="border border-gray-800 bg-white rounded-lg p-6 shadow-sm">
                        <h3 class="text-lg font-semibold text-gray-900 mb-4">Frontend Web Developer</h3>
                        <div class="prose max-w-none">
                            <p class="text-gray-600 mb-6 text-justify">
                                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas id nostrum facilis beatae
                                iusto accusantium consequuntur consectetur commodi ipsum eveniet! Iusto quaerat neque ab
                                doloremque blanditiis in numquam fuga quis.
                                Veritatis voluptatum placeat atque maiores nisi odit error natus ex quasi? Harum amet a
                                repellat velit nostrum recusandae, quis consequuntur ad dolorem repudiandae? At
                                molestias cum vero id doloremque totam?
                                Illo delectus similique fuga. Deserunt tempore doloribus animi cum autem harum,
                                voluptatibus ut, distinctio sit nemo expedita aliquid velit? Ad sint numquam incidunt
                                error voluptates quaerat in dolor officia ipsam.
                                Similique commodi officiis vel sint iusto pariatur possimus, ex rem error. Temporibus,
                                obcaecati officiis similique laudantium voluptas ducimus sed consequuntur maiores ex
                                beatae pariatur rerum inventore quas? Dolorem, voluptatem quibusdam!
                                Vero praesentium hic, consequatur eos repudiandae quo minus officia voluptate quas
                                ducimus enim eligendi. Quisquam, quaerat eveniet asperiores blanditiis architecto cumque
                                mollitia est corporis aspernatur, nulla veritatis, expedita et vitae?
                            </p>



                            <h4 class="text-lg font-semibold text-gray-900 mb-2">Criteria</h4>
                            <ul class="list-disc list-inside text-gray-600 mb-6">
                                <li>Criteria 1</li>
                                <li>Criteria 2</li>
                                <li>Criteria 3</li>
                                <li>Criteria 4</li>
                            </ul>
                        </div>


                    </div>
                </div>
            </div>
        </div>
    </div>
</template>