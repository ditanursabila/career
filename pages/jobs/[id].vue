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

        <div v-if="loading" class="max-w-7xl mx-auto px-4 py-8 text-center">
            Loading job details...
        </div>
        <div v-else-if="error" class="max-w-7xl mx-auto px-4 py-8 text-center text-red-500">
            {{ error }}
        </div>
        <div v-else class="max-w-7xl mx-auto px-4 py-8">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <!-- Job Card -->
                <div class="md:col-span-1">
                    <div class="border border-gray-800 bg-white rounded-lg p-6 shadow-sm">
                        <h2 class="text-xl font-semibold text-gray-900 mb-2">{{ job.name }}</h2>
                        <p class="text-gray-600 text-lg mb-4">{{ job.type }}</p>
                        <div class="flex items-center gap-2 text-gray-500">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24"
                                stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
                            </svg>
                            <span>{{ formatDate(job.deadline) }}</span>
                        </div>
                    </div>
                    <div class="mt-8">
                        <nuxt-link :to="`../jobs/form?job_id=${job.id}`">
                            <button
                                class="w-full md:w-auto px-6 py-3 bg-sky-600 text-white rounded-lg hover:bg-sky-700 transition-all">
                                Apply Now
                            </button>
                        </nuxt-link>
                    </div>
                </div>

                <!-- Job Detail -->
                <div class="md:col-span-2">
                    <div class="border border-gray-800 bg-white rounded-lg p-6 shadow-sm">
                        <h3 class="text-lg font-semibold text-gray-900 mb-4">{{ job.name }}</h3>
                        <div class="prose max-w-none">
                            <p class="text-gray-600 mb-6 text-justify" v-html="job.description"></p>

                            <h4 class="text-lg font-semibold text-gray-900 mb-2">Criteria</h4>
                            <ul class="list-disc list-inside text-gray-600 mb-6">
                                <li v-for="(criterion, index) in job.criteria" :key="index">{{ criterion }}</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const job = ref(null)
const loading = ref(true)
const error = ref(null)

const formatDate = (dateString) => {
    if (!dateString) return '';
    return new Date(dateString).toLocaleDateString('en-US', {
        year: 'numeric',
        month: 'long',
        day: 'numeric'
    });
}

onMounted(async () => {
    try {
        const response = await fetch(`https://astacode.id/api/jobs/${route.params.id}`, {
            method: 'GET',
            headers: {
                'Accept': 'application/json',
                'Content-Type': 'application/json'
            },
        })

        if (!response.ok) {
            throw new Error('Network response was not ok')
        }

        const data = await response.json()
        console.log('Job details:', data)
        job.value = data.data || data
        loading.value = false
    } catch (err) {
        console.error('Error fetching job details:', err)
        error.value = 'Failed to load job details. Please try again later.'
        loading.value = false
    }
})
</script>