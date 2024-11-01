<template>
    <div class="holder">
        <div class="nav">
            <VerticalNav :verticalNav="verticalNav" @changeComponent="switchComponent"></VerticalNav>
        </div>
        <div class="content">
            <ContentHeader></ContentHeader>
            <!-- <DonorDarshboard></DonorDarshboard> -->
            <component :is="currentComponent" />
        </div>
    </div>
</template>

<script setup>
const components = {
  DonorDashboard: defineAsyncComponent(() => import('@/components/donor/Dashboard.vue')),
  DonorDonationForm: defineAsyncComponent(() => import('@/components/donor/DonationForm.vue')),
  DonorDonations: defineAsyncComponent(() => import('@/components/donor/Donations.vue')),
  BloodDrives: defineAsyncComponent(() => import('@/components/donor/BloodDrives.vue')),
  Settings: defineAsyncComponent(() => import('@/components/donor/Settings.vue')),
  Help: defineAsyncComponent(() => import('@/components/donor/Help.vue'))
};

const currentComponent = ref(components.DonorDashboard);

// Function to switch the component based on the event
const switchComponent = (componentName) => {
//   console.log('Switching to component:', componentName); 
  // Check if componentName exists in the components map
  if (components[componentName]) {
    currentComponent.value = components[componentName];
  } else {
    console.warn(`Component "${componentName}" not found.`);
    currentComponent.value = components.DonorDashboard; // Default fallback
  }
};

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
        { name: "Dashboard", icon: "i-tabler-dashboard", component: "donor/Dashboard" },
        { name: "Donate", icon: "i-tabler-heart-handshake", component: "DonorDonationForm" },
        { name: "Donations", icon: "i-tabler:medicine-syrup", component: "DonorDonations" },
        { name: "Blood Drives", icon: "i-tabler:building-community", component: "BloodDrives" },
        { name: "Settings", icon: "i-tabler-settings", component: "Settings" },
        { name: "Help & Center", icon: "i-tabler-help", component: "Help" }
    ]
    },

],
};
</script>

<style scoped>
/* .holder{
    width: 100%;
    background-color: #F2F2F2;
    min-height: 100vh;
    padding: 10px;
}
.nav{
    width: 20%;
    margin-right: 20px;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: start;
} */
.content{
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>
