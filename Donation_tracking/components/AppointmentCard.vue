<template>
    <div class="card">
        <div class="head">
            <div class="title" >
                <span class="mainText">The appointment title long test </span>
            </div>

            <div class="menu">
                <UIcon name="i-octicon:kebab-horizontal-16" dynamic :style="{ color: 'black' }"/>
            </div>
        </div>
        <div class="deco">
            <div class="line" v-for="i in 3">

            </div>
        </div>
        <div class="body">
            <div class="profile">
                <img src="@/assets/images/woman-doctor-5321351_1920-removebg-preview.png" alt="">
            </div>
            <div class="time">
                <span class="normalText">Patient name</span>
                <span class="smallText">12:30 pm</span>
            </div>
        </div>

    </div>
</template>

<script setup>
const colors = ['#e2fde8', '#d9f7fa', '#faead6'];

const set_background = () => {
    const elements = document.getElementsByClassName('card');
    for (let i = 0; i < elements.length; i++) {
        elements[i].style.backgroundColor = colors[i % colors.length];
    }
};

onMounted(() => {
    set_background();
});
</script>

<style scoped>
.card{
    width: 32%;
    height: 150px;
    border-radius: 20px;
    margin-bottom: 10px;
    margin-left: 1%;
    padding: 1%;

}
.head{
    display: flex;
    justify-content: space-between;
    height: 50px;
}
.title{
    max-width: 80%;
    max-height: 50px;
    /* background-color: aquamarine; */
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
    color: var(--vt-nawe-text);

}
.menu{
    border: 2px solid var(--vt-nawe-outline);
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display:flex;
    justify-content: center;
    align-items: center;
}
.body{
    margin-top: 10px;
    width: 100%;
    height: auto;
    /* background-color: blueviolet; */
    display: flex;
    /* justify-content: space-between; */
}
.profile{
    width: 40px;
    height: 40px;
    margin: 1%;
    border-radius: 50%;
    background-color: brown;
    overflow: hidden;
}
.profile img{
    display: block;
    width: 100%;
    height: 100%;
}
.time{
    display: flex;
    width: 50%;
    flex-direction: column;
    justify-content: center;
}
.deco{
    display: flex;
}
.line{
    height: 10px;
    width: 60px;
    margin-left: 10px;
}
</style>
