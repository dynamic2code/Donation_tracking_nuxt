<template>
    <div class="holder">
        <div class="nav">
            <VerticalNav :verticalNav="verticalNav" @changeComponent="switchComponent"></VerticalNav>
        </div>
        <div class="content">
            <ContentHeader></ContentHeader>
            <component :is="currentComponent" />
        </div>

        <DoctorRegisterDoctor></DoctorRegisterDoctor>
            
    </div>
</template>

<script setup>
import { ref } from 'vue';
import { defineAsyncComponent } from 'vue';

// Hardcoded components
const components = {
  Dashboard: defineAsyncComponent(() => import('@/components/doctor/Dashboard.vue')),
  Tasks: defineAsyncComponent(() => import('@/components/doctor/Tasks.vue')),
  Appointments: defineAsyncComponent(() => import('@/components/doctor/Appointment.vue')),
  Calendar: defineAsyncComponent(() => import('@/components/doctor/Calendar.vue')),
//   Settings: defineAsyncComponent(() => import('@/components/doctor/Settings.vue')),
//   Help: defineAsyncComponent(() => import('@/components/doctor/Help.vue')),
  BloodDonations: defineAsyncComponent(() => import('@/components/doctor/BloodDonations.vue')),
//   Performance: defineAsyncComponent(() => import('@/components/doctor/Performance.vue')),
//   Payrolls: defineAsyncComponent(() => import('@/components/doctor/Payrolls.vue')),
//   Invoices: defineAsyncComponent(() => import('@/components/doctor/Invoices.vue')),
//   Employees: defineAsyncComponent(() => import('@/components/doctor/Employees.vue')),
//   Hiring: defineAsyncComponent(() => import('@/components/doctor/Hiring.vue')),
};

// Default component
const default_component = components.Dashboard;

const currentComponent = ref(default_component);

// Function to switch the component based on the event
const switchComponent = (componentName) => {
  // Check if componentName exists in the components map
  if (components[componentName]) {
    currentComponent.value = components[componentName];
  } else {
    console.warn(`Component "${componentName}" not found.`);
    currentComponent.value = default_component;
  }
};

// Vertical navigation structure
const verticalNav = {
  logo: {
    src: "logo.png",
    alt: "Ocupite Logo"
  },
  user: {
    name: "Ali",
    avatar: "user-avatar.png"
  },
  menu: [
    {
      title: "Main Menu",
      items: [
        { name: "Dashboard", icon: "i-tabler-dashboard", component: "Dashboard" },
        { name: "Tasks", icon: "i-tabler-layout-dashboard", component: "Tasks" },
        { name: "Appointments", icon: "i-tabler-calendar", component: "Appointments"},
        { name: "Calendar", icon: "i-tabler-calendar", component: "Calendar" },
        { name: "Settings", icon: "i-tabler-settings", component: "Settings" },
        { name: "Help & Center", icon: "i-tabler-help", component: "Help" },
        { name: "Blood donations", icon: "i-tabler-heart-handshake", component: "BloodDonations" }
      ]
    },
    {
      title: "Team Management",
      items: [
        { name: "Performance", icon: "i-tabler-chart-area", component: "Performance" },
        { name: "Payrolls", icon: "i-tabler-file-dollar", component: "Payrolls" },
        { name: "Invoices", icon: "i-tabler-clock-dollar", component: "Invoices" },
        { name: "Employees", icon: "i-tabler-users-group", component: "Employees" },
        { name: "Hiring", icon: "i-tabler-user-plus", component: "Hiring" }
      ]
    },
    {
      title: "List",
      items: [
        { name: "Salary Information", icon: "i-tabler-moneybag", route: "/salary-information" },
        { name: "Compensation", icon: "i-tabler-chart-infographic", route: "/compensation-breakdown" },
        { name: "Project-specific", icon: "i-tabler-hammer", route: "/project-specific-data" }
      ]
    }
  ],
};
</script>


<style scoped>
.content{
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
}
</style>