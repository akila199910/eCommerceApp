<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
// import { Icon } from "@iconify/vue";

const isScrolled = ref(false);
const isMobileMenuOpen = ref(false);
const navItems = [
    {id: 1, name: "Home", link: "home"},
    {id: 1, name: "Products", link: "products"},
    {id: 1, name: "Categories", link: "categories"},
    {id: 1, name: "Offers", link: "offers"},
    {id: 1, name: "About", link: "about"},
    {id: 1, name: "Contact", link: "contact"},
];

const handleScroll = () => {
    isScrolled.value = window.scrollY > 10;
};

const scrollToSection = (sectionId, event) => {
    event.preventDefault();
    const element = document.getElementById(sectionId);
    if (element) {
        const headerOffset = 80; // Adjust this value based on your header height
        const elementPosition = element.getBoundingClientRect().top;
        const offsetPosition = elementPosition + window.pageYOffset - headerOffset;

        window.scrollTo({
            top: offsetPosition,
            behavior: "smooth"
        });
    }
    isMobileMenuOpen.value = false; // Close mobile menu after clicking
};

onMounted(() => {
    window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll);
});

</script>

<template>
    <header class="sticky top-0 z-50 transition-all duration-300">
        <section :class="['w-full', isScrolled ? 'bg-gray-100/95 backdrop-blur shadow-md py-2' : 'bg-gray-100 py-4']">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex flex-col md:flex-row items-center justify-between gap-3 md:gap-6">
                    <!-- Logo + Mobile Menu Toggle Button -->
                     <div class="flex justify-between items-center w-full md:w-auto">
                        <a href="/" class="text-2xl font-bold text-pink-600 uppercase">Sebiro Technologies</a>
                        <button
                            class="md:hidden text-gray-700 hover:text-indigo-600"
                            aria-label="Toggle mobile menu"
                            @click="isMobileMenuOpen = !isMobileMenuOpen"
                            >
                            <Icon icon="mdi:menu" class="w-6 h-6" />
                        </button>
                     </div>
                     <!-- Search Bar -->
                      <form class=" w-full md:flex-1 max-w-sm" role="search" aria-label="Site search" action="">
                        <label class=" relative w-full" for="">
                            <input type="text" placeholder="Search ..." 
                            class=" w-full px-2 py-2 text-xs border border-gray-300 rounded-full focus:outline-none
                            focus:ring-2 focus:ring-indigo-500 "
                            >

                            <button type="submit" class="absolute right-2 top-1/2 -translate-y-1/2 text-gray-500 hover:text-indigo-500"
                            aria-label="Search button"
                            >
                                <Icon icon="mdi:magnify" class="w-4 h-4" />
                            </button>
                        </label>
                      </form>
                      <!-- icons -->
                       <aside class="flex items-center justify-end space-x-4 w-full md:w-auto ">
                            <button class="relative p-2 text-gray-700 hover:text-pink-600" aria-label="wishlist">
                                <Icon icon="mdi:heart-outline" class="w-5 h-5" />
                                <span class="absolute -top-1 -right-1 bg-pink-500 text-white text-xl rounded-full w-5 h-5
                                flex items-center justify-center">3</span>
                            </button>
                            <button class="relative p-2 text-gray-700 hover:text-pink-600" aria-label="wishlist">
                                <Icon icon="mdi:cart-outline" class="w-5 h-5" />
                                <span class="absolute -top-1 -right-1 bg-pink-500 text-white text-xl rounded-full w-5 h-5
                                flex items-center justify-center">5</span>
                            </button>
                            <button class="relative p-2 text-gray-700 hover:text-pink-600" aria-label="wishlist">
                                <Icon icon="mdi:account-outline" class="w-5 h-5" />
                            </button>
                       </aside>
                </div>
            </div>
        </section>
        <!-- Navbar link -->
        <nav class="bg-pink-950" aria-label="Main navigation">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <ul class="hidden md:flex justify-center py-3 flex-wrap gap-x-6 text-sm font-medium text-white">
                    <li v-for="item in navItems" :key="item.id">
                        <a :href="'#' + item.link" 
                           @click="scrollToSection(item.link, $event)"
                           class="hover:text-pink-300 transition-colors">
                            {{ item.name }}
                        </a>
                    </li>
                </ul>

                <section v-if="isMobileMenuOpen"
                    class="md:hidden mt-2 bg-white rounded-lg shadow-md p-4 space-y-4 text-[#5D4037] text-center"
                    aria-label="Mobile navigation">
                    <a v-for="item in navItems" 
                       :key="item.id" 
                       :href="'#' + item.link"
                       @click="scrollToSection(item.link, $event)"
                       class="block hover:text-pink-600 text-sm font-medium">
                        {{ item.name }}
                    </a>
                </section>
            </div>

        </nav>
    </header>
</template>

