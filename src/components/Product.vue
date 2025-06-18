<script setup>
import { Icon } from '@iconify/vue';
import { ref, onMounted, onUnmounted, computed, onBeforeUnmount } from 'vue';
import image1 from '../assets/img/product/images1.jpeg';
import image2 from '../assets/img/product/images(2).jpeg';
import image3 from '../assets/img/product/images(3).jpeg';
import image4 from '../assets/img/product/images(4).jpeg';
import image5 from '../assets/img/product/images(5).jpeg';
import image6 from '../assets/img/product/images(6).jpeg';
import image7 from '../assets/img/product/images(7).jpeg';
import image8 from '../assets/img/product/images(8).jpeg';
import image9 from '../assets/img/product/images(9).jpeg';
import image10 from '../assets/img/product/images(10).jpeg';
import image11 from '../assets/img/product/images(11).jpeg';
import image12 from '../assets/img/product/images(12).jpeg';
import image13 from '../assets/img/product/images(13).jpeg';
import image14 from '../assets/img/product/images(14).jpeg';
import image15 from '../assets/img/product/images(15).jpeg';

const currentSlide = ref(0);
const productsPerPage = ref(4);

const products = [
    {id:1, name:'image1', price: 100, rating: 4.5, image: image1,discount: 20},
    {id:2, name:'image2', price: 100, rating: 4.5, image: image2,discount: 20},
    {id:3, name:'image3', price: 100, rating: 4.5, image: image3,discount: 20},
    {id:4, name:'image4', price: 100, rating: 4.5, image: image4,discount: 20},
    {id:5, name:'image5', price: 100, rating: 4.5, image: image5,discount: 20},
    {id:6, name:'image6', price: 100, rating: 4.5, image: image6,discount: 20},
    {id:7, name:'image7', price: 100, rating: 4.5, image: image7,discount: 20},
    {id:8, name:'image8', price: 100, rating: 4.5, image: image8,discount: 20},
    {id:9, name:'image9', price: 100, rating: 4.5, image: image9,discount: 20},
    {id:10, name:'image10', price: 100, rating: 4.5, image: image10,discount: 20},
    {id:11, name:'image11', price: 100, rating: 4.5, image: image11,discount: 20},
    {id:12, name:'image12', price: 100, rating: 4.5, image: image12,discount: 20},
    {id:13, name:'image13', price: 100, rating: 4.5, image: image13,discount: 20},
    {id:14, name:'image14', price: 100, rating: 4.5, image: image14,discount: 20},
    {id:15, name:'image15', price: 100, rating: 4.5, image: image15,discount: 20},
];

const totalSlides = computed(() => Math.ceil(products.length / productsPerPage.value));
const visibleProducts = computed(() => {
    const start = currentSlide.value * productsPerPage.value;
    return products.slice(start, start + productsPerPage.value);
});

const nextSlide = ()=>{
    currentSlide.value = currentSlide.value === totalSlides.value -1 ? 0 : currentSlide.value + 1;
};
const prevSlide = ()=>{
    currentSlide.value = currentSlide.value === totalSlides.value -1 ? 0 : currentSlide.value - 1;
};

const handleResize = () => {
    if(window.innerWidth < 640){
        productsPerPage.value = 1;
    }else if(window.innerWidth < 768){
        productsPerPage.value = 2;
    }else if(window.innerWidth < 1024){
        productsPerPage.value = 3;
    }else{
        productsPerPage.value = 4;
    }
};

onMounted(() => {
    handleResize();
    window.addEventListener('resize', handleResize);
});

onBeforeUnmount(() => {
    window.removeEventListener('resize',handleResize);
});
</script>

<template>
    <section class="py-12 scroll-mt-20 bg-gray-50 " id="product">
            <main class=" container mx-auto px-4">
                <header class=" flex justify-between items-center mb-8">
                    <h2 class=" md:text-3xl text-2xl font-bold text-amber-900">Featured Products</h2>
                    <nav class="flex space-x-4" aria-label="Product carousel controls">
                        <button @click="prevSlide"
                            class=" p-2 rounded-full bg-white shadow-md hover:bg-pink-100
                            text-pink-600 transition-colors" aria-label="Previous slide">
                            <Icon icon="line:md:arrow-small-left" class="w-24 h-24" />
                        </button>
                        <button @click="nextSlide"
                            class=" p-2 rounded-full bg-white shadow-md hover:bg-pink-100
                            text-pink-600 transition-colors" aria-label="Next slide">
                            <Icon icon="line:md:arrow-small-right" class="w-24 h-24" />
                        </button>
                    </nav>
                </header>

                <section class=" relative overflow-hidden">
                    <ul class=" grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
                        <li v-for="product in visibleProducts" :key="product.id"
                        class=" bg-white rounded-lg shadow-md overflow-hidden transition-all duration-300
                            hover:scale-105">
                            <article>
                                <figure class=" relative">
                                    <img :src="product.image" :alt="product.name" class=" w-full h-64 object-cover">
                                    <figcaption v-if="product.discount > 0"
                                        class="absolute top-3 right-3 bg-red-500 text-white text-xs font-bold px-2 py-1 rounded-full">
                                        -{{ product.discount }}%
                                    </figcaption>
                                    <button class=" absolute top-3 left-3 p-2 bg-white rounded-full shadow-md
                                    hover:bg-pink-100 text-gray-700 " aria-label="Add to wishlist">
                                        <Icon icon="line-md:heart" width="18" height="18" />
                                    </button>
                                </figure>
                                <section class="p-4">
                                    <div class="flex items-center mb-2">
                                        <Icon v-for="i in 5" :key="i" icon="line-md:star-alt-filled" width="18" height="18"
                                        :class="i <= Math.round(product.rating) ? 'text-yellow-400' : 'text-gray-300' " />
                                        <span class=" text-sm text-gray-500 ml-1">({{ product.rating }})</span>
                                    </div>
                                    <h3 class=" text-lg font-semibold text-gray-800 mb-1">{{ product.name }}</h3>
                                    <footer class=" flex justify-between items-center">
                                        <div>
                                            <span class="text-lg font-bold text-pink-600">${{ product.price * (1 - product.discount / 100).toFixed(2) }}>
                                            </span>
                                            <span v-if="product.discount > 0" class="text-sm text-gray-500 line-through ml-2">
                                                ${{ product.price.toFixed(2) }}></span>
                                        </div>
                                        <button class="p-2 bg-pink-950 rounded-full text-white hover:bg-pink-700 transition-colors"
                                        aria-label="Add to cart">
                                        <Icon icon="icon-park-solid:shopping" width="18" height="18" />
                                    </button>
                                    </footer>
                                </section>
                            </article>
                        </li>
                    </ul>
                </section>
                <nav class=" flex justify-center mt-6 space-x-2" aria-label="Carousel pagination">
                    <button v-for="index in totalSlides" :key="index" @click="currentSlide = index - 1"
                    :class="['w-3 h-3 rounded-full', currentSlide === index - 1 ? 'bg-pink-950' : 'bg-gray-400']"/>
                </nav>
            </main>
    </section>
</template>