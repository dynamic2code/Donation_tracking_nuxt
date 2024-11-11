<template>
    <div class="holders">
        <div class="container">
            <div @click="back">
                <Icon name="i-ic:baseline-arrow-back" style="color: black; font-size: 50px;"></Icon>
            </div>

        </div>
    </div>
</template>

<script setup>
const router = useRouter();
const back = () => {
  router.back();
};
</script>

<style scoped>
.holders{
    /* background-color: white; */
    /* background-color: blueviolet; */
}
.container{
    /* background-color: yellow; */
    justify-content: start;
}
</style>
