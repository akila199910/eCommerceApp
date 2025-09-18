<script setup>
import { ref } from 'vue';
import image1 from '../assets/img/category/download.jpeg';

const categories = ref([
    {id: 1, title: "Category 1", image: image1, description: "Category D1", alt: "Category 1"},
    {id: 2, title: "Category 2", image: image1, description: "Category D2", alt: "Category 2"},
    {id: 3, title: "Category 3", image: image1, description: "Category D3", alt: "Category 3"},
    {id: 4, title: "Category 4", image: image1, description: "Category D4", alt: "Category 4"},
    {id: 5, title: "Category 5", image: image1, description: "Category D5", alt: "Category 5"},
    {id: 6, title: "Category 6", image: image1, description: "Category D6", alt: "Category 6"},
]);
</script>

<template>
    <section id="categories" class=" py-16 scorll-mt-20 bg-white">
        <div class=" container mx-auto px-4">
            <!-- section header -->
             <div class=" text-center mb-12">
                <h2 class=" text-3xl font-bold text-amber-950 mb-3">Explore Our Categories</h2>
                <p class=" text-lg text-gray-800 max-w-2xl mx-auto">Discover a wide range of categories to choose from</p>
             </div>
             <!-- categories grid -->
              <div class=" grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div v-for="(category, index) in categories" :key="index"
                    class=" relative group overflow-hidden rounded-lg shadow-md hover:shadow-lg transition-shadow 
                    duration-300" >
                    <div class="h-64 overflow-hidden">
                        <img :src="category.image" :alt="category.alt" class=" w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class=" absolute inset-0 bg-gradient-to-t from-black/60 via-transparent to-transparent">
                        <div class=" absolute bottom-0 left-0 p-6">
                            <h3 class=" text-xl font-semibold text-white">{{ category.title }}</h3>
                            <p class=" text-gray-200 mt-1">{{ category.description }}</p>
                        </div>
                    </div>
                </div>
              </div>
        </div>
    </section>
</template>