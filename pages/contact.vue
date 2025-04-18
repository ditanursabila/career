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


        <div class="max-w-[85rem] px-4 sm:px-6 lg:px-8 mx-auto">
            <div class="mt-12 max-w-lg mx-auto">
                <div class="flex flex-col border-2 border-gray-300 rounded-xl p-4 sm:p-6 lg:p-8 shadow-lg">
                    <form @submit.prevent="submitForm">
                        <div class="grid gap-4 lg:gap-6">
                            <div>
                                <label for="name" class="block mb-2 text-sm text-gray-700 font-medium">Full Name</label>
                                <input type="text" v-model="formData.name" id="name"
                                    :class="{ 'border-red-500': errors.name }"
                                    class="py-2.5 sm:py-3 px-4 block w-full border-2 border-gray-300 rounded-lg sm:text-sm focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:opacity-50 disabled:pointer-events-none">
                                <p v-if="errors.name" class="mt-1 text-sm text-red-500">{{ errors.name }}</p>
                            </div>

                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 lg:gap-6">
                                <div>
                                    <label for="email"
                                        class="block mb-2 text-sm text-gray-700 font-medium">Email</label>
                                    <input type="email" v-model="formData.email" id="email"
                                        :class="{ 'border-red-500': errors.email }"
                                        class="py-2.5 sm:py-3 px-4 block w-full border-2 border-gray-300 rounded-lg sm:text-sm focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:opacity-50 disabled:pointer-events-none">
                                    <p v-if="errors.email" class="mt-1 text-sm text-red-500">{{ errors.email }}</p>
                                </div>

                                <div>
                                    <label for="phone" class="block mb-2 text-sm text-gray-700 font-medium">Phone
                                        Number</label>
                                    <input type="text" v-model="formData.phone" id="phone"
                                        :class="{ 'border-red-500': errors.phone }"
                                        class="py-2.5 sm:py-3 px-4 block w-full border-2 border-gray-300 rounded-lg sm:text-sm focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:opacity-50 disabled:pointer-events-none">
                                    <p v-if="errors.phone" class="mt-1 text-sm text-red-500">{{ errors.phone }}</p>
                                </div>
                            </div>

                            <div>
                                <label for="message"
                                    class="block mb-2 text-sm text-gray-700 font-medium">Message</label>
                                <textarea v-model="formData.message" id="message" rows="4"
                                    :class="{ 'border-red-500': errors.message }"
                                    class="py-2.5 sm:py-3 px-4 block w-full border-2 border-gray-300 rounded-lg sm:text-sm focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:opacity-50 disabled:pointer-events-none"></textarea>
                                <p v-if="errors.message" class="mt-1 text-sm text-red-500">{{ errors.message }}</p>
                            </div>
                        </div>

                        <div class="mt-6 grid">
                            <button type="submit" :disabled="isSubmitting"
                                class="w-full py-3 px-4 inline-flex justify-center items-center gap-x-2 text-sm font-medium rounded-lg border-2 border-transparent bg-sky-600 text-white hover:bg-sky-700 disabled:opacity-50 disabled:cursor-not-allowed focus:outline-hidden focus:ring-2 focus:ring-sky-500 focus:ring-offset-2 transition-all">
                                {{ isSubmitting ? 'Submitting...' : 'Submit' }}
                            </button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'
import Swal from 'sweetalert2'

const router = useRouter()
const isSubmitting = ref(false)
const errors = ref({})

const formData = ref({
    name: '',
    email: '',
    phone: '',
    message: ''
})

const submitForm = async () => {
    isSubmitting.value = true
    errors.value = {}

    try {
        const form = new FormData()
        Object.keys(formData.value).forEach(key => {
            if (formData.value[key]) {
                form.append(key, formData.value[key])
            }
        })

        const response = await fetch('https://astacode.id/api/contact', {
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
            text: 'Your message has been sent successfully',
            confirmButtonColor: '#0284c7'
        })

        formData.value = { name: '', email: '', phone: '', message: '' }
        router.push('/contact')

    } catch (error) {
        console.error('Error submitting form:', error)
        await Swal.fire({
            icon: 'error',
            title: 'Error',
            text: error.message || 'Failed to submit form. Please try again.',
            confirmButtonColor: '#0284c7'
        })
    } finally {
        isSubmitting.value = false
    }
}
</script>