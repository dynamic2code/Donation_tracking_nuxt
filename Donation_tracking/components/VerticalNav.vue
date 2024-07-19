<template>
    <div>
      <div class="top">
        <div class="profile">
          <img src="@/assets/images/logo-no-background.png" alt="">
        </div>
        <div>
          <UAvatar
            size="md"
            src="https://avatars.githubusercontent.com/u/739984?v=4"
            alt="Avatar"
          />
        </div>
      </div>
      <div class="navPart" v-for="(section, index) in verticalNav.menu" :key="index">
        <span class="normalText bold">{{ section.title }}</span>
        <button class="navButton" v-for="(item, idx) in section.items" :key="idx">
          <UIcon :name="item.icon" dynamic :style="{ color: 'black' }" />
          <span class="mainText">{{ item.name }}</span>
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
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
          { name: "Dashboard", icon: "i-tabler-dashboard", route: "/dashboard" },
          { name: "Tasks", icon: "i-tabler-layout-dashboard", route: "/tasks" },
          { name: "Calendar", icon: "i-tabler-calendar", route: "/calendar" },
          { name: "Settings", icon: "i-tabler-settings", route: "/settings" },
          { name: "Help & Center", icon: "i-tabler-help", route: "/help" }
        ]
      },
      {
        title: "Team Management",
        items: [
          { name: "Performance", icon: "i-tabler-chart-area", route: "/performance" },
          { name: "Payrolls", icon: "i-tabler-file-dollar", route: "/payrolls" },
          { name: "Invoices", icon: "i-tabler-clock-dollar", route: "/invoices" },
          { name: "Employees", icon: "i-tabler-users-group", route: "/employees" },
          { name: "Hiring", icon: "i-tabler-user-plus", route: "/hiring" }
        ]
      },
      {
        title: "List",
        items: [
          { name: "Salary Information", icon: "i-tabler-moneybag", route: "/salary-information" },
          { name: "Compensation Breakdown", icon: "i-tabler-chart-infographic", route: "/compensation-breakdown" },
          { name: "Project-specific Data", icon: "i-tabler-hammer", route: "/project-specific-data" }
        ]
      }
    ],
    upgradePlan: {
      status: "free trial",
      daysLeft: 5
    }
  };
  </script>
  
  <style scoped>
  .top {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .profile {
    width: 50%;
  }
  
  .navPart {
    width: 100%;
    display: flex;
    flex-direction: column;
  }
  
  .navButton {
    display: flex;
    align-items: center;
    width: 100%;
    padding: 5px;
    margin-bottom: 5px;
    border-radius: 10px;
    background-color: #F2F2F2;
    transition: background-color 0.3s, border 0.3s;
  }
  
  .navButton:hover {
    width: 100%;
    padding: 5px;
    margin-bottom: 5px;
    border-radius: 10px;
    background-color: white;
    border: 0.5px solid rgb(168, 168, 168);
  }
  
  .navButton > * {
    margin-left: 10px;
  }
  </style>
  