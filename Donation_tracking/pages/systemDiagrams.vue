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
  
      <!-- Main Content -->
      <div class="w-4/5 bg-gray-100 p-8">
        <div class="max-w-3xl mx-auto bg-white shadow-md rounded-lg p-6">
          <h1 class="text-4xl font-bold text-center mb-6">System Designs and Diagrams</h1>
          <p class="text-lg mb-4">

          </p>
          <h1 class="text-4xl font-bold text-center mb-6">Blood Donation Process</h1>
    
          <h2 class="text-2xl font-semibold mb-4">User Story</h2>
          <p class="text-lg mb-4">
            <strong>Title:</strong> Blood Donation Process<br>
            <strong>As a</strong> blood donor,<br>
            <strong>I want to</strong> donate my blood at a hospital,<br>
            <strong>so that</strong> it can be used to save a life.
          </p>

          <h2 class="text-2xl font-semibold mb-4">Acceptance Criteria</h2>

          <h3 class="text-xl font-semibold mb-2">Donation Form:</h3>
          <ul class="list-disc list-inside mb-4">
            <li><strong>Given</strong> I am at the hospital,</li>
            <li><strong>When</strong> I express my desire to donate blood,</li>
            <li><strong>Then</strong> I am provided with a donation form to fill out with my personal and medical information.</li>
          </ul>

          <h3 class="text-xl font-semibold mb-2">Qualification Assessment:</h3>
          <ul class="list-disc list-inside mb-4">
            <li><strong>Given</strong> I have completed the donation form,</li>
            <li><strong>When</strong> a doctor reviews my form,</li>
            <li><strong>Then</strong> the doctor performs a preliminary health check to ensure I meet the qualification criteria for blood donation.</li>
          </ul>

          <h3 class="text-xl font-semibold mb-2">Blood Collection and Testing:</h3>
          <ul class="list-disc list-inside mb-4">
            <li><strong>Given</strong> I am qualified to donate,</li>
            <li><strong>When</strong> my blood is drawn,</li>
            <li><strong>Then</strong> my blood is sent to the lab for testing.</li>
          </ul>

          <h3 class="text-xl font-semibold mb-2">Communication of Test Results:</h3>
          <ul class="list-disc list-inside mb-4">
            <li><strong>Given</strong> my blood is being tested,</li>
            <li><strong>When</strong> the results are available,</li>
            <li><strong>Then</strong> I am communicated with regarding any issues found in my blood samples,</li>
            <li><strong>And</strong> if no issues are found, I am informed that my donation was successful.</li>
          </ul>

          <h3 class="text-xl font-semibold mb-2">Storage of Blood:</h3>
          <ul class="list-disc list-inside mb-4">
            <li><strong>Given</strong> my blood has been tested and cleared,</li>
            <li><strong>When</strong> it is ready for storage,</li>
            <li><strong>Then</strong> my blood is safely stored in the hospital's blood bank.</li>
          </ul>

          <h3 class="text-xl font-semibold mb-2">Utilization of Blood:</h3>
          <ul class="list-disc list-inside mb-4">
            <li><strong>Given</strong> my blood is stored in the blood bank,</li>
            <li><strong>When</strong> a patient needs a blood transfusion,</li>
            <li><strong>Then</strong> my blood is used to save a life.</li>
          </ul>

          <h2 class="text-2xl font-semibold mt-6 mb-4">Project Objectives</h2>
          <ol class="list-decimal list-inside mb-4">
            <li>Develop an online platform for donors to fill out and submit donation forms, along with initial assessments to determine their eligibility.</li>
            <li>Maintain a secure, comprehensive digital record of all donations to ensure accurate tracking and easy access to information.</li>
            <li>Implement an automated follow-up system to communicate with donors about their donation status and any post-donation updates or requirements.</li>
            <li>Create a robust search feature that allows administrators to quickly locate specific donations based on criteria such as donor name, donation type, date, and status.</li>
            <li>Integrate powerful analytics tools to analyze donation patterns, donor demographics, and the effectiveness of donation campaigns.</li>
            <li>Develop a method to track donations throughout the entire process, from submission to utilization, ensuring transparency and accountability.</li>
          </ol>

          <h2 class="text-2xl font-semibold mt-6 mb-4">Project Scope</h2>
          <ul class="list-disc list-inside mb-4">
            <li>
              <strong>Scope Statement:</strong>
              <p class="ml-4">The project includes developing a web-based application with features for user registration, donation tracking, documentation management, and communication tools (Africa's Talking API for now). It excludes third-party integrations at this stage.</p>
            </li>
            <li>
              <strong>Deliverables:</strong>
              <p class="ml-4">The deliverables include a fully functional web application, user manuals, training materials, and a support plan.</p>
            </li>
            <li>
              <strong>Inclusions and Exclusions:</strong>
              <p class="ml-4">The project includes developing the backend system using Django and the frontend using Nuxt.js .</p>
            </li>
            <li>
              <strong>Constraints and Assumptions:</strong>
              <p class="ml-4">One key assumption is that all donation units will be labeled with a QR code to aid in identification and tracking. we are starting with blood donation then we'll move to more types of donation</p>
            </li>
          </ul>

          <h1 class="text-4xl font-bold text-center mb-6">Diagrams</h1>
          <h2 class="text-2xl font-semibold mt-6 mb-4">Data flow Diagram</h2>
          <img src="/Untitled Diagram.drawio (2).png" alt="">
          <a href="/Untitled Diagram.drawio.pdf" target="_blank"><h3>Open PDF 📄</h3></a>

          <h2 class="text-2xl font-semibold mt-6 mb-4">Sequence Diagram</h2>
          <img src="/sequence.drawio.png" alt="">
          <a href="/sequence Diagram.drawio.pdf" target="_blank"><h3>Open PDF 📄</h3></a>

          <h2 class="text-2xl font-semibold mt-6 mb-4">Class Relation Diagram</h2>
          <img src="/class diagram.drawio.png" alt="">
          <a href="/class diagram.drawio.pdf" target="_blank"><h3>Open PDF 📄</h3></a>

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