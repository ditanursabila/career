<template>
    <div>
        <div class="relative h-[200px] shadow-lg overflow-hidden">
            <img src="assets/img/bgjob.jpg" alt="Jobs Header Image" class="w-full h-full object-cover" />
            <div class="absolute inset-0 bg-black/60" />
            <div class="absolute inset-0 flex flex-col items-center justify-center gap-4">
                <h1 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white" data-aos="fade-down"
                    data-aos-duration="800">
                    Let's find your job!
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

        <div class="max-w-4xl px-4 py-10 sm:px-6 lg:px-8 lg:py-14 mx-auto">
            <div class="bg-white rounded-xl shadow-lg p-4 sm:p-7 border border-gray-200">
                <form @submit.prevent="handleSubmit" enctype="multipart/form-data">
                    <div class="grid sm:grid-cols-12 gap-4 sm:gap-6">
                        <!-- Job Position -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Posisi *</label>
                        </div>
                        <div class="sm:col-span-9">
                            <div v-if="isLoading" class="flex items-center space-x-2">
                                <div class="animate-pulse h-10 bg-gray-200 rounded w-full"></div>
                            </div>
                            <div v-else>
                                <input type="text" v-model="formData.job_id" readonly
                                    class="py-2 px-4 block w-full border border-gray-200 bg-gray-50 rounded-lg text-sm">
                                <span v-if="errors.job_id" class="text-red-500 text-xs mt-1">{{ errors.job_id[0]
                                }}</span>
                            </div>
                        </div>

                        <!-- Name -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Full Name *</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="text" v-model="formData.name" placeholder="Your full name" required
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                            <span v-if="errors.name" class="text-red-500 text-xs mt-1">{{ errors.name[0] }}</span>
                        </div>

                        <!-- Email -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Email *</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="email" v-model="formData.email" placeholder="you@example.com" required
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                            <span v-if="errors.email" class="text-red-500 text-xs mt-1">{{ errors.email[0] }}</span>
                        </div>

                        <!-- Gender -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Gender</label>
                        </div>
                        <div class="sm:col-span-9">
                            <div class="flex gap-4">
                                <label class="inline-flex items-center">
                                    <input type="radio" v-model="formData.gender" name="gender" value="male"
                                        class="form-radio text-sky-500">
                                    <span class="ml-2">Male</span>
                                </label>
                                <label class="inline-flex items-center">
                                    <input type="radio" v-model="formData.gender" name="gender" value="female"
                                        class="form-radio text-sky-500">
                                    <span class="ml-2">Female</span>
                                </label>
                            </div>
                        </div>

                        <!-- Address -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Address</label>
                        </div>
                        <div class="sm:col-span-9">
                            <textarea v-model="formData.alamat" rows="3" placeholder="Your complete address"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500"></textarea>
                        </div>

                        <!-- Phone -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Phone</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="tel" v-model="formData.telp" placeholder="+62 xxx-xxxx-xxxx"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- LinkedIn -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">LinkedIn Profile</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="url" v-model="formData.linkedin" placeholder="https://linkedin.com/in/username"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- GitHub -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">GitHub Profile</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="url" v-model="formData.github" placeholder="https://github.com/username"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- Portfolio -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Portfolio Website</label>
                        </div>
                        <div class="sm:col-span-9">
                            <input type="url" v-model="formData.portfolio" placeholder="https://your-portfolio.com"
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500">
                        </div>

                        <!-- CV Upload -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">Resume/CV</label>
                        </div>
                        <div class="sm:col-span-9">
                            <div class="border-2 border-dashed border-gray-300 rounded-lg p-4">
                                <input type="file" @change="handleFileUpload" accept=".pdf,.doc,.docx" class="block w-full text-sm text-gray-500
                                file:me-4 file:py-2 file:px-4
                                file:rounded-lg file:border-0
                                file:text-sm file:font-medium
                                file:bg-sky-50 file:text-sky-700
                                hover:file:bg-sky-100">
                                <p class="text-xs text-gray-500 mt-2">Accepted formats: PDF, DOC, DOCX. Max size: 5MB
                                </p>
                                <span v-if="errors.cv" class="text-red-500 text-xs mt-1">{{ errors.cv[0] }}</span>
                            </div>
                        </div>

                        <!-- About You -->
                        <div class="sm:col-span-3">
                            <label class="block text-sm font-medium text-gray-700 mb-2">About You</label>
                        </div>
                        <div class="sm:col-span-9">
                            <textarea v-model="formData.tentang" rows="4"
                                placeholder="Tell us about yourself, your experience, and why you're interested in this position..."
                                class="py-2 px-4 block w-full border border-gray-300 rounded-lg text-sm focus:border-sky-500 focus:ring-sky-500"></textarea>
                        </div>

                        <div class="sm:col-span-12 flex justify-end mt-6">
                            <button type="submit" :disabled="loading"
                                class="py-3 px-8 inline-flex justify-center items-center gap-2 rounded-lg border border-transparent font-medium bg-sky-600 text-white hover:bg-sky-700 focus:outline-none focus:ring-2 focus:ring-sky-500 focus:ring-offset-2 transition-all text-sm disabled:opacity-50">
                                {{ loading ? 'Submitting...' : 'Submit Application' }}
                            </button>
                        </div>
                    </div>
                </form>
            </div>
        </div>

    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useRoute, useRouter } from 'vue-router'
import Swal from 'sweetalert2'

const route = useRoute()
const router = useRouter()
const loading = ref(false)
const errors = ref({})
const isLoading = ref(true)

const formData = ref({
    job_id: '',
    name: '',
    email: '',
    gender: '',
    alamat: '',
    telp: '',
    linkedin: '',
    github: '',
    portfolio: '',
    tentang: '',
    cv: null
})

onMounted(async () => {
    if (route.query.job_id) {
        await fetchJobDetails(route.query.job_id)
    } else {
        isLoading.value = false
        Swal.fire({
            icon: 'warning',
            title: 'No Job Selected',
            text: 'Please select a job position from the jobs page',
            confirmButtonColor: '#0284c7'
        }).then(() => {
            router.push('/jobs')
        })
    }
})

const fetchJobDetails = async (jobId) => {
    try {
        const response = await fetch(`https://astacode.id/api/jobs/${jobId}`)

        if (!response.ok) {
            throw new Error('Job not found')
        }

        const jobData = await response.json()

        formData.value.job_id = jobData.data.name || 'Position Not Available'

    } catch (error) {
        console.error('Error fetching job details:', error)
        Swal.fire({
            icon: 'error',
            title: 'Error',
            text: 'Unable to load job details. Please try again.',
            confirmButtonColor: '#0284c7'
        }).then(() => {
            router.push('/jobs')
        })
    } finally {
        isLoading.value = false
    }
}

const handleFileUpload = (e) => {
    formData.value.cv = e.target.files[0]
}

const submitForm = async () => {
    loading.value = true
    errors.value = {}

    try {
        const form = new FormData()
        Object.keys(formData.value).forEach(key => {
            if (formData.value[key]) {
                form.append(key, formData.value[key])
            }
        })

        form.append('job_id', route.query.job_id)

        const response = await fetch('https://astacode.id/api/jobs/apply', {
            method: 'POST',
            body: form
        })

        const data = await response.json()

        if (!response.ok) {
            if (response.status === 422) {
                errors.value = data.errors
                await Swal.fire({
                    icon: 'error',
                    title: 'Validation Error',
                    text: 'Please check the form for errors',
                    confirmButtonColor: '#0284c7'
                })
                return
            }
            throw new Error(data.message || 'Something went wrong')
        }


        await Swal.fire({
            icon: 'success',
            title: 'Success!',
            text: 'Your application has been submitted successfully',
            confirmButtonColor: '#0284c7'
        })
        router.push('/jobs')

    } catch (error) {
        console.error('Error submitting form:', error)

        await Swal.fire({
            icon: 'error',
            title: 'Error',
            text: error.message || 'Failed to submit application. Please try again.',
            confirmButtonColor: '#0284c7'
        })
    } finally {
        loading.value = false
    }
}
const validateForm = () => {
    const requiredFields = ['job_id', 'name', 'email']
    const errors = {}

    requiredFields.forEach(field => {
        if (!formData.value[field]?.trim()) {
            errors[field] = ['This field is required']
        }
    })

    if (!formData.value.cv) {
        errors.cv = ['Please upload your CV']
    }

    return errors
}

const handleSubmit = async () => {
    const validationErrors = validateForm()

    if (Object.keys(validationErrors).length > 0) {
        errors.value = validationErrors
        await Swal.fire({
            icon: 'warning',
            title: 'Required Fields Missing',
            text: 'Please fill in all required fields',
            confirmButtonColor: '#0284c7'
        })
        return
    }

    await submitForm()
}
</script>