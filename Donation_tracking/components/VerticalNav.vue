<template>
    <div class="full">
      <div class="top">
        <NuxtLink to="/"class="profile">
          <img src="@/assets/images/nawe-health-system-favicon-black.png" alt="">
        </NuxtLink>
          <UAvatar
            size="md"
            src="https://avatars.githubusercontent.com/u/739984?v=4"
            alt="Avatar"
            :style="{border: '1px solid black'}"
          />
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
const props = defineProps({
  verticalNav: {
    type: Object,
    required: true
  }
});

  </script>
  
  <style scoped>
  /* .full{
    height: 100%;
    display: flex;
    flex-direction: column;
  } */
  .top {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .profile {
    width: 50%;
  }
  .profile img{
    width: 50px;
    height: 50px;
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
    padding: 10px; /* Increased padding for better visual consistency */
    margin-bottom: 5px;
    border-radius: 10px;
    background-color: #F2F2F2;
    border: 1px solid transparent; /* Set a transparent border to keep size consistent */
    transition: background-color 0.3s, box-shadow 0.3s;
    box-sizing: border-box; /* Include padding and border in the element's total width and height */
  }

  .navButton:hover {
    background-color: white;
    border: 1px solid var(--vt-nawe-outline);
    /* box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); */
  }
  
  .navButton > * {
    margin-left: 10px;
  }
  </style>
  