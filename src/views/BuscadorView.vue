<script>
import Card from '@/components/Card.vue'
import Search from '@/components/Search.vue'
import Loading from '@/components/Loading.vue'
export default {
    components: {
        Card,
        Search,
        Loading,
    },
    data: () => ({
        loading: false,
        gifs: [],
    }),
    methods: {
        async getGifs(search, tipo) {
            this.loading = true;
            const data = await fetch(`https://api.giphy.com/v1/${tipo}/search?api_key=wUXT26e40eOtge3DhaWbrAo7gLS0ng6h&q=${search}`);
            // const data = await fetch(`https://api.giphy.com/v1/stickers/search?api_key=wUXT26e40eOtge3DhaWbrAo7gLS0ng6h&q=${search}`);
            const res = await data.json();
            this.gifs = res.data;
            this.loading = false;
            console.log(this.gifs);
        },
    }
}

</script>


<template>
    <div class="my-10 mx-7">
        <!-- Title -->      
        <h2 
            class="text-center text-4xl md:text-6xl font-extrabold text-gray-300 tracking-tight"
        >
            🎯 Buscador de <span class="text-green-500">GIFs</span>
        </h2>
        <p class="text-center mt-4 text-gray-400 text-lg max-w-xl mx-auto leading-relaxed">
            Busca tus <span class="font-semibold text-green-500">GIFs</span> o <span class="font-semibold text-blue-600">Stickers</span> favoritos usando la API de Giphy.
        </p>


        <!-- Search -->
         <div class="my-8">
            <Search @buscar="getGifs"/>
         </div>

         <!-- Loading -->
        <div class="flex justify-center my-12">
            <Loading v-if="loading"/>
        </div>

         <!-- Cards -->
         <div class="columns-1 sm:columns-2 md:columns-3 lg:columns-4 gap-4">
            <div 
                v-for="gif in gifs" :key="gif.id" 
                class="mb-10 break-inside-avoid rounded-lg shadow-lg bg-[#0f0c294f] transform transition duration-300 hover:scale-105 hover:shadow-2xl"
            >
                <Card :gifs="gif"/>
            </div>
         </div>

         <!-- No results -->
         <div v-if="gifs.length === 0 && loading === false" class="text-center text-gray-600">
            <p>No se encontraron resultados</p>
         </div>


    </div>
</template>