<script setup>
import image1 from '../assets/img/product/images1.jpeg';

</script>

<template>
    <div id="about" class=" min-h-screen scroll-mt-20 bg-gradient-to-b from-gray-50 to-white py-12 px-4 sm:px-6 lg:px-8">
        <div class=" max-w-7xl mx-auto">
            <div class=" flex flex-col lg:flex-row gap-12 mb-12">
                <!-- image section -->
                <div class=" lg:w-1/2">
                    <div class=" relative rounded-2xl overflow-hidden h-96 shadow-xl">
                        <img :src="image1" alt="About Image" class=" w-full h-full object-cover">
                        <div class=" absolute inset-0 bg-gradient-to-t from-black opacity-50"></div>
                        <div class=" absolute bottom-0 left-0 p-6 text-white">
                            <h3 class=" text-2xl font-bold">Since 2025</h3>
                            <p class="mt-2"> Crafting perfumes with passion</p>
                        </div>
                    </div>
                </div>
                <!-- text content -->
                 <div class=" lg:w-1/2 flex flex-col justify-center">
                    <h2 class=" text-4xl font-bold text-amber-900 mb-6">About Us</h2>
                    <p class=" text-lg text-gray-600 mb-4 text-justify">
                        Lorem ipsum, dolor sit amet consectetur adipisicing elit. 
                        Doloribus, vitae sed, eveniet perferendis iste nam repellendus consequatur 
                        distinctio, tempora explicabo voluptate dolores error maxime velit 
                        quibusdam placeat tenetur dolor nesciunt!
                    </p>
                    <div class="grid grid-cols-2 gap-4 mt-4">
                        <div class=" bg-white rounded-lg p-4 shadow-sm border border-gray-100 ">
                            <h4 class=" font-semibold text-pink-600 ">500+</h4>
                            <p class="break-words text-wrap overflow-hidden text-ellipsis">Unique Fragrances</p>
                        </div>
                        <div class=" bg-white rounded-lg p-4 shadow-sm border border-gray-100 ">
                            <h4 class=" font-semibold text-pink-600 ">50+</h4>
                            <p class="break-words text-wrap overflow-hidden text-ellipsis">Unique Worldwide</p>
                        </div>
                        <div class=" bg-white rounded-lg p-4 shadow-sm border border-gray-100 ">
                            <h4 class=" font-semibold text-pink-600 ">100+</h4>
                            <p class="break-words text-wrap overflow-hidden text-ellipsis">Customer Satisfication</p>
                        </div>
                        <div class=" bg-white rounded-lg p-4 shadow-sm border border-gray-100 ">
                            <h4 class=" font-semibold text-pink-600 ">24/7</h4>
                            <p class="break-words text-wrap overflow-hidden text-ellipsis">Customer Support</p>
                        </div>
                    </div>
                 </div>
            </div>
        </div>
    </div>
</template>