<template>
    <div class="min-h-screen flex">
    <!-- Vertical Navigation Bar -->
      <nav class="w-1/5 bg-gray-800 text-white p-4">
        <div class="space-y-4">
          <NuxtLink to="/" class="block py-2 px-4 rounded hover:bg-gray-700">Home</NuxtLink>
          <NuxtLink to="/mainApp" class="block py-2 px-4 rounded hover:bg-gray-700">Main App</NuxtLink>
          <NuxtLink to="/djangoDocumentation" class="block py-2 px-4 rounded hover:bg-gray-700">Django Documentation</NuxtLink>
          <NuxtLink to="/nuxtDocumentation" class="block py-2 px-4 rounded hover:bg-gray-700">Nuxt Documentation</NuxtLink>
          <NuxtLink to="/systemDiagrams" class="block py-2 px-4 rounded hover:bg-gray-700">System Diagrams and Design</NuxtLink>
        </div>
      </nav>

    </div>
</template>

<script setup>
</script>

<style scoped>
</style>