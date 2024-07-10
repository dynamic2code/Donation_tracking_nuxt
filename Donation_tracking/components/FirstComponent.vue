<template>
    <div class="halves">
        <div class="first">
            <div class="head">
                <span class="xlText" >Simplifying & Streamlining The Health Industry</span>
                <div class="features">
                    <FeatureComponent v-for="feature in features" :key="index" :feature="feature"></FeatureComponent>
                </div>

            </div>
        </div>
        <div class="second">
            <div class="image">
                <img src="@/assets/images/woman-doctor-5321351_1920-removebg-preview.png" alt="">
            </div>
        </div>
    </div>
</template>

<script setup>
const features =[
    {
        image: '/Blood-Bag.png',
        heading: 'Blood donation',
        text: 'click to see how we are making blood donation, blood drives, and donor messaging easier'
    },
    {
        image: '/Money-Bag.png',
        heading: 'Money Donation',
        text: 'click to see how we are making money donation direct to the patients bill possible'
    },
    {
        image: '/Customer-Relationship.png',
        heading: 'Hospital staff',
        text: 'click to see how we are making hospital staff management easier'
    },
    {
        image: '/Shipment-Monitor.png',
        heading: 'Inventory tracking',
        text: 'click to see how we are making hospital inventory management possible online'
    }
]
</script>

<style scoped>
.halves{
    display: flex;
    height: 80vh;
}
.first{
    width: 60%;
    padding-top: 50px;
}
.second{
    width: 40%;
}
.image{
    margin: 20px;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background-color: blueviolet;
    border-top-right-radius: 50px;
    border-bottom-left-radius: 50px;
}
.image img{
    display: block;
    width: 100%;
    height: auto;
    border-top-right-radius: 50px;
    border-bottom-left-radius: 50px;
}
.features {
    display: flex;
    flex-wrap: wrap;
  /* gap: 20px; */
}
</style>
