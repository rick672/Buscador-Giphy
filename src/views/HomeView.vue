<template>
    <div class="container mx-auto px-4 py-16">
        <div class="max-w-4xl mx-auto text-center">
            <h1 class="text-6xl font-bold mb-6 bg-gradient-to-r from-blue-300 to-purple-600 bg-clip-text text-transparent">
                Bienvenido a GifHub
            </h1>
            <p class="text-xl text-gray-400 mb-12">
                Tu destino favorito para encontrar los mejores GIFs y Stickers
            </p>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-16">
                <div class="bg-white/20 p-8 rounded-xl shadow-lg hover:shadow-xl transition-shadow">
                    <div class="text-4xl mb-4">🎯</div>
                    <h3 class="text-xl font-semibold mb-2 text-white">Búsqueda Precisa</h3>
                    <p class="text-gray-400">
                        Encuentra exactamente lo que buscas con nuestro potente motor de búsqueda
                    </p>
                </div>
                <div class="bg-white/20 p-8 rounded-xl shadow-lg hover:shadow-xl transition-shadow">
                    <div class="text-4xl mb-4">🚀</div>
                    <h3 class="text-xl font-semibold mb-2 text-white">Rápido y Fácil</h3>
                    <p class="text-gray-400">
                        Interfaz intuitiva y resultados instantáneos
                    </p>
                </div>
            </div>

            <router-link 
                to="/buscador" 
                class="inline-block bg-green-600 hover:bg-green-700 text-white px-8 py-4 rounded-lg text-lg font-semibold transition-colors"
            >
                Comenzar a Buscar
            </router-link>
        </div>

        <div class="mt-16 text-center">
            <p class="text-sm text-gray-500">
                Powered by GIPHY API
            </p>
        </div>
    </div>
</template>