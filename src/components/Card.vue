<script>
export default {
    props: {
        gifs: {
            type: Object,
            required: true,
        }
    }
}
</script>


<template>
    <div class="">
        <div class="text-center">
            <a :href="gifs.images.original.url" target="_blank">
                <img 
                    :src="gifs.images.original.url" 
                    alt="gif"
                    loading="lazy"
                    class="w-full h-auto rounded-t-lg" 
                    :alt="gifs.id" 
                >
            </a>
        </div>
        <div class="m-2 font-semibold text-gray-200 text-center text-md">
            <h3>{{ gifs.username ? gifs.username : gifs.title }}</h3>
        </div>
        <div class="flex justify-around text-sm pb-2">
            <div>
                <a :href="gifs.images.original.url" target="_blank" class="text-blue-500">Ver Original  </a>
            </div>
            <div>
                <p class="text-gray-500 text-center">
                    {{ gifs.images.original.width }}x{{ gifs.images.original.height }}
                </p>
            </div>
        </div>
    </div>

</template>