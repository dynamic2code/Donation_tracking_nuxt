<template>
    <div class="min-h-screen flex">
      <!-- Vertical Navigation Bar -->
      <nav class="w-1/5 bg-gray-800 text-white p-4">
        <ul class="space-y-4">
          <li><router-link to="/" class="block py-2 px-4 rounded hover:bg-gray-700">Home</router-link></li>
          <li><router-link to="/documentation" class="block py-2 px-4 rounded hover:bg-gray-700">Main Documentation</router-link></li>
          <li><router-link to="/djangoDocumentation" class="block py-2 px-4 rounded hover:bg-gray-700">Django Documentation</router-link></li>
          <li><router-link to="/nuxtDocumentation" class="block py-2 px-4 rounded hover:bg-gray-700">Nuxt Documentation</router-link></li>
          <li><router-link to="/systemDiagrams" class="block py-2 px-4 rounded hover:bg-gray-700">System Diagrams and Design</router-link></li>
        </ul>
      </nav>
  
      <!-- Main Content -->
      <div class="w-4/5 bg-gray-100 p-8">
        <div class="max-w-3xl mx-auto bg-white shadow-md rounded-lg p-6">
          <h1 class="text-4xl font-bold text-center mb-6">Frontend documentation</h1>
  
          <h2 class="text-2xl font-semibold mt-6 mb-4">Join Us!</h2>
          <p class="text-lg mb-4">
            Follow our progress on <a href="https://github.com/dynamic2code/Donation_tracking" class="text-blue-500 underline">GitHub Django</a> or <a href="https://github.com/dynamic2code/Donation-_tracking" class="text-blue-500 underline">GitHub Nuxt</a>, where you can find all the details and how to contribute. Stay updated with our latest news and milestones. I can't wait to build something great together! 🎉
          </p>
        </div>
      </div>
    </div>
</template>
  
<script setup>

</script>
  
<style scoped>

</style> 
