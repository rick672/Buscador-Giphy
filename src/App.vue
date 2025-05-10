<script setup>
import { RouterLink, RouterView } from 'vue-router'
// Componentes
import NavBar from '@/components/NavBar.vue'
import Footer from '@/components/Footer.vue'
</script>

<template>
    <div class="min-h-screen flex flex-col bg-gradient-to-r from-[#24243e] via-[#302b63] to-[#0f0c29]">
        <NavBar />
        <RouterView class="min-h-screen" />
        <Footer />
    </div>
</template>

<style scoped>
/* div {
    background: #0f0c29; 
    background: -webkit-linear-gradient(to right, #24243e, #302b63, #0f0c29);  
    background: linear-gradient(to right, #24243e, #302b63, #0f0c29);

} */
</style>