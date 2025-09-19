<script setup>
import { Icon } from '@iconify/vue';

</script>

<template>
    <div id="contact" class=" min-h-screen scroll-mt-20 bg-pink-950 py-12 px-4 sm:px-6 lg:px-8">
        <div class=" max-w-7xl mx-auto">
            <!-- section header -->
            <div class=" text-center mb-12">
                <h1 class=" text-4xl font-serif font-bold text-white mb-4">Cantact Us</h1>
                <p class=" text-lg text-gray-200 max-w-2xl mx-auto">
                    Have a question? Need help? We're here to help.
                </p>
            </div>
            <div class=" grid grid-cols-1 lg:grid-cols-2 gap-12">
                <div class=" bg-white p-8 rounded-lg shadow-xl border border-gray-100">
                    <h2 class=" text-2xl font-serif font-semibold text-gray-900 mb-6">Send Us a Message</h2>
                    <form class=" space-y-6" action="">
                        <div>
                            <label for="name" class="block text-sm font-medium text-gray-800 mb-1">
                                Your Name
                            </label>
                            <input type="text" name="" id="name" class="w-full px-4 py-3 border border-gray-200 rounded-lg focus:ring-2 focus:ring-pink-500
                            focus:border-transparent" placeholder="Enter your name" />
                        </div>

                        <div>
                            <label for="email" class="block text-sm font-medium text-gray-800 mb-1">
                                Email Address
                            </label>
                            <input type="email" name="" id="email" class="w-full px-4 py-3 border border-gray-200 rounded-lg focus:ring-2 focus:ring-pink-500
                            focus:border-transparent" placeholder="Enter your email" />
                        </div>

                        <div>
                            <label for="message" class="block text-sm font-medium text-gray-800 mb-1">
                                Your Message
                            </label>
                            <textarea type="text" name="" id="message" rows="5"
                                class="w-full px-4 py-3 border border-gray-200 rounded-lg focus:ring-2 focus:ring-pink-500
                                focus:border-transparent" placeholder="Your Message">
                            </textarea>
                        </div>
                        <button class="w-full bg-pink-700 hover:bg-pink-800 text-white py-3 px-6 rounded-lg
                        transition-duration-300 font-medium shadow-md ">Send Message</button>
                    </form>
                </div>
                <div class=" space-y-8">
                    <div class=" bg-white p-8 rounded-lg shadow-xl border border-gray-100">
                        <h2 class=" text-2xl font-serif font-semibold text-gray-900 mb-6">Cantact Informations</h2>
                        <div class=" space-y-6">
                            <div class="flex items-start">
                                <div class=" bg-pink-200 p-3 rounded-full mr-4">
                                    <Icon icon="fa-solid:phone" class=" text-pink-950 text-lg" width="24" height="24"/>
                                </div>
                                <div >
                                    <h3 class="text-lg font-medium text-gray-900">Phone</h3>
                                    <p class=" text-gray-800">0702024999</p>
                                    <p class=" text-gray-600">Mon-Fri:9am-5pm</p>
                                </div>
                            </div>

                            <div class="flex items-start">
                                <div class=" bg-pink-200 p-3 rounded-full mr-4">
                                    <Icon icon="fa-solid:envelope" class=" text-pink-950 text-lg" width="24" height="24"/>
                                </div>
                                <div class=" flex flex-col w-full break-words">
                                    <h3 class="text-lg font-medium text-gray-900">Email</h3>
                                    <p class=" text-gray-800">akilaungaw@gmail.com</p>
                                    <p class=" text-gray-600">akilayanga@gmail.com</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>