<template>
    <div class="full">

        <div class="add">
            <button @click="add">
                <UIcon name="i-ic:sharp-create" dynamic :style="{ color: 'black' }"/>
            </button>
        </div>
        <AddTask v-if="showAddTask" ></AddTask>

    </div>

</template>

<script setup>

const showAddTask = ref(false)
const add = () => {
    showAddTask.value = true
}
</script>

<style scoped>
.add{
    position: fixed;
    display: flex;
    justify-content: center;
    align-items: center;
    bottom: 20px;
    right: 20px ;
    height: 50px;
    width: 50px;
    border-radius: 50%;
    background-color: var(--vt-nawe-outline);
    border: 2px solid var(--vt-nawe-outline);
    z-index: 4;
}
</style>
