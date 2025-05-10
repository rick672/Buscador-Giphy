<script setup>
import { ref } from 'vue'
import { useRoute } from 'vue-router';
import { RouterLink, RouterView } from 'vue-router';

const route = useRoute();
const isMenuOpen = ref(false)

const navigation = [
    { name: 'Home', path: '/', current: route.path === '/' },
    { name: 'About', path: '/about', current: route.path === '/about' },
    { name: 'Buscador', path: '/buscador', current: route.path === '/buscador' },
]

</script>

<template>
    <nav class="bg-white border-gray-200 dark:bg-gradient-to-l from-[#24243e] via-[#302b63] to-[#0f0c29]">
        <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
            <RouterLink
                to="/"
                class="flex items-center space-x-3 rtl:space-x-reverse"
            >
                <img 
                    src="https://flowbite.com/docs/images/logo.svg" 
                    class="h-8" alt="Flowbite Logo" 
                />
                <span 
                    class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white"
                >
                    API de Giphy
                </span>
            </RouterLink
            >
            <button
                @click="isMenuOpen = !isMenuOpen"
                type="button"
                class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg md:hidden hover:bg-gray-100 dark:hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:focus:ring-gray-600 cursor-pointer"
            >
                <span class="sr-only">Abrir menú principal</span>
                <svg class="w-5 h-5" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
                    <path
                        stroke="currentColor"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M1 1h15M1 7h15M1 13h15"
                    />
                </svg>
            </button>
            <div :class="['w-full text-center md:block md:w-auto', isMenuOpen ? 'block' : 'hidden']">
                <ul
                    class="font-medium flex flex-col p-4 md:p-0 mt-4 border border-gray-100 rounded-lg 
                    bg-gray-50 md:flex-row md:space-x-8 rtl:space-x-reverse md:mt-0 md:border-0 
                    md:bg-white dark:bg-gray-800 md:dark:bg-transparent dark:border-gray-700"
                >
                    <li v-for="item in navigation" :key="item.name">
                        <RouterLink
                            :to="item.path"
                            class="hover:bg-white/20 block py-2 px-3 rounded md:bg-transparent md:p-0 text-gray-700 hover:text-blue-600 dark:text-gray-300 dark:hover:text-blue-100  transition-colors"
                            active-class="text-blue-600 dark:text-white"
                        >
                            {{ item.name }}
                        </RouterLink>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

</template>