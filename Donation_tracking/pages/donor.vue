<template>
    <div class="holder">
        <div class="nav">
            <VerticalNav :verticalNav="verticalNav"></VerticalNav>
        </div>
        <div class="content">
            <ContentHeader></ContentHeader>
            
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
        { name: "Donate", icon: "i-tabler-heart-handshake", route: "/tasks" },
        { name: "Donations", icon: "i-tabler:medicine-syrup", route: "/calendar" },
        { name: "Blood Drives", icon: "i-tabler:building-community", route: "/calendar" },
        { name: "Settings", icon: "i-tabler-settings", route: "/settings" },
        { name: "Help & Center", icon: "i-tabler-help", route: "/help" }
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
}
.content{
    width: 79%;
    background-color: white ;
    min-height: 600px;
    border-radius: 10px;
} */
</style>