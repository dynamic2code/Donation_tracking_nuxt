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

          <!-- <h2 class="text-2xl font-semibold mt-6 mb-4">landing Page inspiration</h2>
          <img src="/Medica Hospital.jpeg" alt=""> -->

          <h2 class="text-2xl font-semibold mt-6 mb-4">Main app inspiration </h2>
          <img src="/GRZogVxaUAAJy19.jpeg" alt="">

          <h2 class="text-2xl font-semibold mt-6 mb-4">User Groups and Their Needs</h2>

          <h3 class="text-xl font-semibold mt-4 mb-2">1. Hospital Management:</h3>
          <p class="text-lg mb-4">
            <ul class="list-disc ml-6">
              <li><strong>Dashboard:</strong> Overview of operations, financials, and KPIs.</li>
              <li><strong>Staff Management:</strong> Scheduling, performance tracking, and communication tools.</li>
              <li><strong>Resource Allocation:</strong> Inventory tracking for supplies and equipment.</li>
              <li><strong>Reporting:</strong> Detailed reports on hospital performance, patient outcomes, and financial health.</li>
            </ul>
          </p>

          <h3 class="text-xl font-semibold mt-4 mb-2">2. Doctors:</h3>
          <p class="text-lg mb-4">
            <ul class="list-disc ml-6">
              <li><strong>Patient Records:</strong> Access to medical histories, test results, and treatment plans.</li>
              <li><strong>Appointment Management:</strong> Scheduling and reminders.</li>
              <li><strong>Communication Tools:</strong> Secure messaging with colleagues (nurses, lab technicians etc) and patients.</li>
              <li><strong>Clinical Decision Support:</strong> Tools for diagnostics and treatment planning.</li>
            </ul>
          </p>

          <h3 class="text-xl font-semibold mt-4 mb-2">3. Nurses:</h3>
          <p class="text-lg mb-4">
            <ul class="list-disc ml-6">
              <li><strong>Task Management:</strong> Daily schedules, reminders, and task lists.</li>
              <li><strong>Patient Monitoring:</strong> Tools for tracking vital signs and symptoms.</li>
              <li><strong>Medication Administration:</strong> Records of medications given and schedules.</li>
              <li><strong>Communication:</strong> Access to doctors and other nurses.</li>
            </ul>
          </p>

          <h3 class="text-xl font-semibold mt-4 mb-2">4. Patients:</h3>
          <p class="text-lg mb-4">
            <ul class="list-disc ml-6">
              <li><strong>Appointment Scheduling:</strong> Easy booking and reminders.</li>
              <li><strong>Health Records:</strong> Access to personal medical history, test results, and treatment plans.</li>
              <li><strong>Billing:</strong> Clear information on bills and payment options.</li>
              <li><strong>Communication:</strong> Direct messaging with healthcare providers.</li>
            </ul>
          </p>

          <h3 class="text-xl font-semibold mt-4 mb-2">5. Donors:</h3>
          <p class="text-lg mb-4">
            <ul class="list-disc ml-6">
              <li><strong>Donation Portal:</strong> Interface for making contributions and filling out blood donation forms.</li>
              <li><strong>Impact Tracking:</strong> Information on donation usage and impact.</li>
              <li><strong>Communication:</strong> Updates and acknowledgments from the hospital.</li>
            </ul>
          </p>


        </div>
      </div>
    </div>
</template>
  
<script setup>

</script>
  
<style scoped>
  * {
    color: black;
  }

  a {
    color: rgb(18, 125, 175);
  }

  .nav-item {
    color: white;
  }
</style> 
