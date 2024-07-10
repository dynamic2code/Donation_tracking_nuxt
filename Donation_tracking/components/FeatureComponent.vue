<template>
    <div class="feature">
        <div class="image_raw" >
            <div class="image" >
                <img :src="feature.image" alt="">
            </div>
        </div>
        <div class="text">
            <span class="largeText">{{ feature.heading }}</span>
            <span class="normalText">{{ feature.text }}</span>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
  feature: {
    type: Object,
    required: true,
    default: () => ({
      image: '',
      heading: '',
      text: ''
    })
  }
})

</script>

<style scoped>
.feature{
    display: flex;
    width: 45%;
    /* background-color: aquamarine; */
    margin: 5px;
}
.image_raw{
    width: 30%;
    margin-right: 5px;
    /* background-color: blue; */
}
.image{
    width: auto;
    height: auto;
    padding: 5px;
    background-color: #E7F5FE;
    border-radius: 10px;
    display: flex;
    justify-content: center;
    align-items: center;

}
.image img{
    width: 30px;
}
.text{
    display: flex;
    flex-direction: column;
}

</style>