<template>
    <div>
        <div class="relative h-[200px] shadow-lg overflow-hidden">
            <img src="assets/img/bgcontact.jpg" alt="Jobs Header Image" class="w-full h-full object-cover" />
            <div class="absolute inset-0 bg-black/60" />
            <div class="absolute inset-0 flex flex-col items-center justify-center gap-4">
                <h1 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white" data-aos="fade-down"
                    data-aos-duration="800">
                    Contact us!
                </h1>
                <nav class="flex items-center gap-2 text-sm md:text-base text-white/90" data-aos="fade-up"
                    data-aos-duration="800" data-aos-delay="200">
                    <nuxt-link to="/" class="hover:text-sky-400 transition-colors">
                        Home
                    </nuxt-link>
                    <span class="text-white/60">/</span>
                    <span class="text-sky-400">Contact</span>
                </nav>
            </div>
        </div>

        <!-- Contact Us -->
        <div class="max-w-[85rem] px-4 sm:px-6 lg:px-8 mx-auto">
            <div class="mt-12 max-w-lg mx-auto">
             
                <div class="flex flex-col border-2 border-gray-300 rounded-xl p-4 sm:p-6 lg:p-8 shadow-lg">
                    <form>
                        <div class="grid gap-4 lg:gap-6">
                      
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 lg:gap-6">
                                <div>
                                    <label for="hs-firstname-contacts-1"
                                        class="block mb-2 text-sm text-gray-700 font-medium">First Name</label>
                                    <input type="text" name="hs-firstname-contacts-1" id="hs-firstname-contacts-1"
                                        class="py-2.5 sm:py-3 px-4 block w-full border-2 border-gray-300 rounded-lg sm:text-sm focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:opacity-50 disabled:pointer-events-none">
                                </div>

                                <div>
                                    <label for="hs-lastname-contacts-1"
                                        class="block mb-2 text-sm text-gray-700 font-medium">Last Name</label>
                                    <input type="text" name="hs-lastname-contacts-1" id="hs-lastname-contacts-1"
                                        class="py-2.5 sm:py-3 px-4 block w-full border-2 border-gray-300 rounded-lg sm:text-sm focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:opacity-50 disabled:pointer-events-none">
                                </div>
                            </div>

                           
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 lg:gap-6">
                                <div>
                                    <label for="hs-email-contacts-1"
                                        class="block mb-2 text-sm text-gray-700 font-medium">Email</label>
                                    <input type="email" name="hs-email-contacts-1" id="hs-email-contacts-1"
                                        autocomplete="email"
                                        class="py-2.5 sm:py-3 px-4 block w-full border-2 border-gray-300 rounded-lg sm:text-sm focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:opacity-50 disabled:pointer-events-none">
                                </div>

                                <div>
                                    <label for="hs-phone-number-1"
                                        class="block mb-2 text-sm text-gray-700 font-medium">Phone Number</label>
                                    <input type="text" name="hs-phone-number-1" id="hs-phone-number-1"
                                        class="py-2.5 sm:py-3 px-4 block w-full border-2 border-gray-300 rounded-lg sm:text-sm focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:opacity-50 disabled:pointer-events-none">
                                </div>
                            </div>

                            <div>
                                <label for="hs-about-contacts-1"
                                    class="block mb-2 text-sm text-gray-700 font-medium">Message</label>
                                <textarea id="hs-about-contacts-1" name="hs-about-contacts-1" rows="4"
                                    class="py-2.5 sm:py-3 px-4 block w-full border-2 border-gray-300 rounded-lg sm:text-sm focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:opacity-50 disabled:pointer-events-none"></textarea>
                            </div>
                        </div>

                        <div class="mt-6 grid">
                            <button type="submit"
                                class="w-full py-3 px-4 inline-flex justify-center items-center gap-x-2 text-sm font-medium rounded-lg border-2 border-transparent bg-sky-600 text-white hover:bg-sky-700 focus:outline-hidden focus:ring-2 focus:ring-sky-500 focus:ring-offset-2 transition-all">
                                Submit
                            </button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>