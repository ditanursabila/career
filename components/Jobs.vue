<template>
    <div
        class="grid grid-cols-1 sm:grid-cols-3 md:grid-cols-3 gap-4 md:gap-6 mt-6 sm:mt-8 md:mt-10 px-4 sm:px-8 md:px-32">
        <div v-if="loading" class="text-white text-center col-span-3">
            Loading jobs...
        </div>
        <div v-else-if="error" class="text-red-500 text-center col-span-3">
            {{ error }}
        </div>
        <template v-else>
            <nuxt-link v-for="job in displayedJobs" :key="job.id" :to="`../jobs/${job.id}`">
                <div
                    class="border border-white/20 bg-white/10 rounded-lg p-6 hover:bg-white/20 transition-all duration-300">
                    <h2 class="text-xl font-semibold text-white mb-2">{{ job.name }}</h2>
                    <p class="text-white/80 text-lg mb-4">{{ job.type }}</p>
                    <div class="flex items-center gap-2 text-white/70">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24"
                            stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
                        </svg>
                        <span>{{ formatDate(job.deadline) }}</span>
                    </div>
                </div>
            </nuxt-link>
        </template>
    </div>
</template>

<script setup>
const props = defineProps({
    limit: {
        type: Number,
        default: null
    },
    loading: {
        type: Boolean,
        default: false
    },
    error: {
        type: String,
        default: null
    }
})

const jobs = ref([])
const loading = ref(true)
const error = ref(null)

const searchQuery = ref('')
const filteredJobs = computed(() => {
    if (!searchQuery.value) return jobs.value

    return jobs.value.filter(job =>
        job.name.toLowerCase().includes(searchQuery.value.toLowerCase())
    )
})

const formatDate = (dateString) => {
    if (!dateString) return '';
    return new Date(dateString).toLocaleDateString('en-US', {
        year: 'numeric',
        month: 'long',
        day: 'numeric'
    });
}

const displayedJobs = computed(() => {
    if (props.limit) {
        return filteredJobs.value.slice(0, props.limit)
    }
    return filteredJobs.value
})

const searchJobs = (query) => {
    searchQuery.value = query
}

defineExpose({
    searchJobs
})

onMounted(async () => {
    try {
        const response = await fetch('https://astacode.id/api/jobs', {
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
        jobs.value = Array.isArray(data.data.data) ? data.data.data : data.data
        loading.value = false
    } catch (error) {
        console.error('Error fetching jobs:', error)
        error.value = 'Failed to load jobs. Please try again later.'
        loading.value = false
    }
})
</script>