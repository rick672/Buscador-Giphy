<template>
<!--
  This example requires updating your template:

  ```
  <html class="h-full">
  <body class="h-full">
  ```
-->
  <!-- En Español -->
    <main class="grid min-h-full place-items-center px-6 py-24 sm:py-32 lg:px-8">
    <div class="text-center">
        <p class="text-2xl font-semibold text-indigo-300">404</p>
        <h1 class="mt-4 text-5xl font-semibold tracking-tight text-balance text-gray-300 sm:text-7xl">Pagina no encontrada</h1>
        <p class="mt-6 text-lg font-medium text-pretty text-gray-400 sm:text-xl/8">Disculpa, pero parece que la página que estás buscando no existe.</p>
        <div class="mt-10 flex items-center justify-center gap-x-6">
        <router-link to="/" class="rounded-md bg-blue-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-xs hover:bg-blue-500 focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-600">Volver al inicio</router-link>
        </div>
    </div>
    </main>

</template>