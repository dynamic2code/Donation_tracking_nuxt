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
          <img :src="item.icon" :alt="item.name">
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
          { name: "Dashboard", icon: "/dashboard.png", route: "/dashboard.png" },
          { name: "Tasks", icon: "tasks-icon", route: "/tasks" },
          { name: "Calendar", icon: "calendar-icon", route: "/calendar" },
          { name: "Settings", icon: "settings-icon", route: "/settings" },
          { name: "Help & Center", icon: "help-icon", route: "/help" }
        ]
      },
      {
        title: "Team Management",
        items: [
          { name: "Performance", icon: "performance-icon", route: "/performance" },
          { name: "Payrolls", icon: "payrolls-icon", route: "/payrolls" },
          { name: "Invoices", icon: "invoices-icon", route: "/invoices" },
          { name: "Employees", icon: "employees-icon", route: "/employees" },
          { name: "Hiring", icon: "hiring-icon", route: "/hiring" }
        ]
      },
      {
        title: "List",
        items: [
          { name: "Salary Information", icon: "salary-icon", route: "/salary-information" },
          { name: "Compensation Breakdown", icon: "compensation-icon", route: "/compensation-breakdown" },
          { name: "Project-specific Data", icon: "project-data-icon", route: "/project-specific-data" }
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
    background-color: white;
    border: 1px solid black;
  }
  
  .navButton > * {
    margin-left: 10px;
  }
  </style>
  