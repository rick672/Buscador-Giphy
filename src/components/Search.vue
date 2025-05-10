<script>
export default {
    data: () => ({
        search: '',
        tipo: 'gifs',
    }),
    methods: {
        getData() {
            console.log(this.search);            
            console.log(this.tipo);
            this.$emit('buscar', this.search, this.tipo);
            this.search = '';
        }
    }
}
</script>

<template>
    <div class="text-center flex justify-center">
        <form 
            @submit.prevent="getData" 
            class="w-full max-w-md p-6 rounded-xl shadow-md space-y-4 bg-white/20 backdrop-blur-md border border-white/20 text-white"
            
        >
            <input 
                v-model.trim="search" 
                type="text" 
                class="w-full p-3 rounded-md border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500 text-center" 
                placeholder="Buscar..."
            >
            <!-- radiobuttons -->
            <div class="flex justify-around">
                <label class="flex items-center gap-2 cursor-pointer">
                    <input
                        type="radio"
                        name="tipo"
                        value="gifs"
                        v-model="tipo"
                        class="accent-green-600"
                    />
                    <span>GIF</span>
                </label>
                <label class="flex items-center gap-2 cursor-pointer">
                    <input
                        type="radio"
                        name="tipo"
                        value="stickers"
                        v-model="tipo"
                        class="accent-blue-600"
                    />
                    <span>Sticker</span>
                </label>
            </div>
            <button
                type="submit"
                class="w-full bg-green-600 hover:bg-green-700 text-white py-2 rounded-md transition-colors"
            >
                🔎 Buscar
            </button>
        </form>
    </div>
</template>