<template>
    <div class="full">
        <AppointmentCard v-for="i in 50"></AppointmentCard>
        

        <div class="add">
            <button @click="add">
                <UIcon name="i-ic:sharp-create" dynamic :style="{ color: 'black' }"/>
            </button>
        </div>
        <DoctorSetAppointment v-if="showAddTask" ></DoctorSetAppointment>

    </div>

</template>

<script setup>

const showAddTask = ref(false)
const add = () => {
    showAddTask.value = true
}
</script>

<style scoped>
.full{
    width: 100%;
    height: 100%;
    padding-left: 10px;
    padding-right: 10px;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    /* background-color: blue; */
    overflow: auto;    
}
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
