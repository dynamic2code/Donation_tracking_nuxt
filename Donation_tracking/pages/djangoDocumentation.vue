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
          <h1 class="text-4xl font-bold text-center mb-6">API Documentation</h1>
          <pre class="bg-gray-200 p-4 rounded">
            <code>
[
  {
    "endpoint": "/api/v1/doctors/",
    "method": "POST",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "body": {
      "hospital": 1,
      "first_name": "John",
      "second_name": "Doe",
      "email": "johndoe@example.com",
      "phone_number": "1234567890"
    }
  },
  {
    "endpoint": "/api/v1/doctors/",
    "method": "GET",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/doctors/{id}/",
    "method": "GET",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/doctors/{id}/",
    "method": "PUT",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "body": {
      "hospital": 1,
      "first_name": "John",
      "second_name": "Doe",
      "email": "johndoe@example.com",
      "phone_number": "1234567890"
    }
  },
  {
    "endpoint": "/api/v1/doctors/{id}/",
    "method": "DELETE",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/donors/",
    "method": "POST",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "body": {
      "first_name": "Jane",
      "second_name": "Doe",
      "gender":"F/M",
      "email": "janedoe@example.com",
      "phone_number": "0987654321",
      "town": "Springfield",
      "date_of_birth": "1990-01-01",
      "blood_type": "O+",
      "last_donation": "2023-01-01"
    }
  },
  {
    "endpoint": "/api/v1/donors/",
    "method": "GET",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/donors/{id}/",
    "method": "GET",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/donors/{id}/",
    "method": "PUT",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "body": {
      "first_name": "Jane",
      "last_name": "Doe",
      "email": "janedoe@example.com",
      "phone_number": "0987654321",
      "town": "Springfield",
      "date_of_birth": "1990-01-01",
      "blood_type": "O+",
      "last_donation": "2023-01-01"
    }
  },
  {
    "endpoint": "/api/v1/donors/{id}/",
    "method": "DELETE",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/hospitals/",
    "method": "POST",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "body": {
      "name": "City Hospital",
      "address": "123 Main St",
      "town": "Springfield",
      "phone_number": "555-1234",
      "email": "contact@cityhospital.com"
    }
  },
  {
    "endpoint": "/api/v1/hospitals/",
    "method": "GET",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/hospitals/{id}/",
    "method": "GET",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/hospitals/{id}/",
    "method": "PUT",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "body": {
      "name": "City Hospital",
      "address": "123 Main St",
      "town": "Springfield",
      "phone_number": "555-1234",
      "email": "contact@cityhospital.com"
    }
  },
  {
    "endpoint": "/api/v1/hospitals/{id}/",
    "method": "DELETE",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/donations/",
    "method": "POST",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "body": {
      "donor": 1,
      "hospital": 2,
      "doctor": 3,
      "donation_type": "blood/money/medication",
      "body_part": null,
      "amount": 100.0,
      "blood_volume": 1, //pint
      "hemoglobin_level": 13.5,
      "payment_method": "Credit Card",
      "transaction_id": "abc123"
    }
  },
  {
    "endpoint": "/api/v1/donations/",
    "method": "GET",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/donations/{id}/",
    "method": "GET",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/donations/{id}/",
    "method": "PUT",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "body": {
      "donor": 1,
      "hospital": 2,
      "doctor": 3,
      "donation_type": 1,
      "body_part": null,
      "amount": 100.0,
      "blood_volume": 0.5,
      "blood_type": "O+",
      "hemoglobin_level": 13.5,
      "date_of_last_donation": "2023-12-01",
      "donation_date": "2024-01-15",
      "purpose": "Charity",
      "payment_method": "Credit Card",
      "transaction_id": "abc123"
    }
  },
  {
    "endpoint": "/api/v1/donations/{id}/",
    "method": "DELETE",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/donations/search/",
    "method": "GET",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "params": {
      "blood_type": "O+"
    },
  }
  {
    "endpoint": "/api/v1/appointments/",
    "method": "POST",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "body": {
      "donor": 1,
      "doctor": 1,
      "hospital": 1,
      "appointment_date": "2023-01-01T10:00:00Z",
      "reason": "Blood donation",
      "status": "Scheduled"
    }
  },
  {
    "endpoint": "/api/v1/appointments/",
    "method": "GET",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/appointments/{id}/",
    "method": "GET",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  },
  {
    "endpoint": "/api/v1/appointments/{id}/",
    "method": "PUT",
    "headers": {
      "Content-Type": "application/json",
      "Authorization": "Bearer your-token"
    },
    "body": {
      "donor": 1,
      "doctor": 1,
      "hospital": 1,
      "appointment_date": "2023-01-01T10:00:00Z",
      "reason": "Blood donation",
      "status": "Scheduled"
    }
  },
  {
    "endpoint": "/api/v1/appointments/{id}/",
    "method": "DELETE",
    "headers": {
      "Authorization": "Bearer your-token"
    }
  }
]

            </code>
          </pre>
  
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
