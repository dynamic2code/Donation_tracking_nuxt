<template>
    <div v-if="showComponent" class="holder">
        <div class="hold">
            <div class="cancel">
                <UIcon @click="close" name="i-ic:baseline-close" dynamic :style="{ color: 'black', height: '40px' }"/>
            </div>            
        </div>        
    </div>
</template>

<script setup>
import { ref } from 'vue';

// Define a ref to control visibility
const showComponent = ref(true);

// Close function to hide the component
const close = () => {
    showComponent.value = false;
};
</script>

<style scoped>
.holder{
    position: fixed;
    top: 0;
    z-index: 4;
    left: 0;
    background-color: rgba(0, 0, 0, 0.6);
    /* background-color: aquamarine; */
    justify-content: center;
    align-items: center;
}
.hold{
    width: 800px;
    height: 500px;
    /* background-color: #962d2d; */
    border-radius: 20px;
    border: 2px solid var(--vt-nawe-outline);
    background-color: var(--vt-nawe-white);
    z-index: 5;
}
.cancel{
    width:100%;
    height: 10%;
    display: flex;
    justify-content: end;
    align-items: center;
    padding-right: 2%;
    /* background-color: black; */
}
</style>
