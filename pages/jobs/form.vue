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
                    <span class="text-sky-400">Form</span>
                </nav>
            </div>
        </div>


        <!-- Card Section -->
        <div class="max-w-4xl px-4 py-10 sm:px-6 lg:px-8 lg:py-14 mx-auto">
            <div class="bg-white rounded-xl shadow-lg p-4 sm:p-7 border border-gray-200">
                <form>
                    <div class="grid sm:grid-cols-12 gap-4 sm:gap-6">
                        <!-- Position -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Position</label>
                        </div>
                        <div class="sm:col-span-9">
                            <select
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                                <option value="">Select position</option>
                                <option value="frontend">Frontend Developer</option>
                                <option value="backend">Backend Developer</option>
                                <option value="mobile">Mobile Developer</option>
                            </select>
                        </div>

                        <!-- Full Name -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Full Name</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="text" placeholder="Your full name"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- Gender -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Gender</label>
                        </div>
                        <div class="sm:col-span-9">
                            <div class="flex gap-4">
                                <label class="inline-flex items-center">
                                    <input type="radio" name="gender" value="male" class="form-radio text-sky-500">
                                    <span class="ml-2">Male</span>
                                </label>
                                <label class="inline-flex items-center">
                                    <input type="radio" name="gender" value="female" class="form-radio text-sky-500">
                                    <span class="ml-2">Female</span>
                                </label>
                            </div>
                        </div>

                        <!-- Address -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Address</label>
                        </div>
                        <div class="sm:col-span-9">
                            <textarea rows="3" placeholder="Your complete address"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500"></textarea>
                        </div>

                        <!-- Email -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Email</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="email" placeholder="you@example.com"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- Phone -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Phone</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="tel" placeholder="+62 xxx-xxxx-xxxx"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- LinkedIn -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">LinkedIn Profile</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="url" placeholder="https://linkedin.com/in/username"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- GitHub -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">GitHub Profile</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="url" placeholder="https://github.com/username"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- Portfolio -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Portfolio Website</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="url" placeholder="https://your-portfolio.com"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- Social Media -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Social Media</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="text" placeholder="Instagram/Twitter username"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- CV Upload -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Resume/CV</label>
                        </div>
                        <div class="sm:col-span-9">
                            <div class="border-2 border-dashed border-gray-300 rounded-lg p-4">
                                <input type="file" accept=".pdf,.doc,.docx" class="block w-full text-sm text-gray-500
                                file:me-4 file:py-2 file:px-4
                                file:rounded-lg file:border-0
                                file:text-sm file:font-medium
                                file:bg-sky-50 file:text-sky-700
                                hover:file:bg-sky-100">
                                <p class="text-xs text-gray-500 mt-2">Accepted formats: PDF, DOC, DOCX. Max size: 5MB
                                </p>
                            </div>
                        </div>

                        <!-- About You -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">About You</label>
                        </div>
                        <div class="sm:col-span-9">
                            <textarea rows="4"
                                placeholder="Tell us about yourself, your experience, and why you're interested in this position..."
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500"></textarea>
                        </div>

                        <!-- Submit Button -->
                        <div class="sm:col-span-12 flex justify-end mt-6">
                            <button type="submit"
                                class="py-3 px-8 inline-flex justify-center items-center gap-2 rounded-lg border border-transparent font-medium bg-sky-600 text-white hover:bg-sky-700 focus:outline-none focus:ring-2 focus:ring-sky-500 focus:ring-offset-2 transition-all text-sm">
                                Submit Application
                            </button>
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>