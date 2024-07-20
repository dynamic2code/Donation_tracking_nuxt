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
};
</script>

<style scoped>
</style>
