<script setup>
import { RouterLink, RouterView } from 'vue-router';

import { useRoute } from 'vue-router';

const route = useRoute();
const navigation = [
    { name: 'Home', path: '/', current: route.path === '/' },
    { name: 'About', path: '/about', current: route.path === '/about' },
    { name: 'Buscador', path: '/buscador', current: route.path === '/buscador' },
]

</script>

<template>
    <footer class="bg-white rounded-lg shadow-sm dark:bg-gradient-to-l from-[#24243e] via-[#302b63] to-[#0f0c29] m-4">
        <div class="w-full max-w-screen-xl mx-auto p-4 md:py-8">
            <div class="sm:flex sm:items-center sm:justify-between">
                <RouterLink 
                    to="/"
                    class="flex items-center mb-4 sm:mb-0 space-x-3 rtl:space-x-reverse">
                    <img src="https://flowbite.com/docs/images/logo.svg" class="h-8" alt="Flowbite Logo" />
                    <span class="self-center text-2xl font-semibold whitespace-nowrap dark:text-white">Buscador de Gifs</span>
                </RouterLink>
                <ul class="flex flex-wrap gap-4 items-center mb-6 text-sm font-medium text-gray-500 sm:mb-0 dark:text-gray-400">
                    <li v-for="item in navigation" :key="item.name">
                        <RouterLink :to="item.path" class="text-white hover:text-gray-300 dark:hover:text-gray-400"
                            >{{ item.name }}</RouterLink
                        >
                    </li>
                </ul>
            </div>
            <hr class="my-6 border-gray-200 sm:mx-auto dark:border-gray-700 lg:my-8" />
            <span class="block text-sm text-gray-500 sm:text-center dark:text-gray-400">© 2025 <a href="https://github.com/rick672" class="hover:underline">Ricardo™</a>. All Rights Reserved.</span>
        </div>
    </footer>

</template>