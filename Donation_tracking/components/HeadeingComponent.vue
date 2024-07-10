<template>
    <div class="holder">
        <div class="warning" >
            <span class="buttonText">Prototype use only</span>            
        </div>

        <div class="container" >
            <div>
                <img src="@/assets/images/logo-no-background.png" alt="">
            </div>
            <div>
                <NuxtLink to="/documentation" class="secondary_button" > 
                    <span class="normalText">documentation</span>
                </NuxtLink>
                <NuxtLink to="/documentation" class="secondary_button" > 
                    <span class="normalText">Contact</span>
                </NuxtLink>
                <NuxtLink to="/about" class="secondary_button" > 
                    <span class="normalText">about</span>
                </NuxtLink>

                <NuxtLink to="/donation" class="primary_button" > 
                    <span class="buttonText" > Go to dash board</span>
                </NuxtLink>

            </div>
        </div>
    </div>
</template>

<script setup>
</script>

<style scoped>
.holder {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: auto;
}
.warning{
    background-color: rgb(223, 151, 151);
    width: 100%;
    height: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.container{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 70px;
    /* background-color: brown; */
}
img{
    width: auto;
    height: 50px;
}
</style>