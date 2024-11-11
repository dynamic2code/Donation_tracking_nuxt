<template>
    <div class="full" >
        <NuxtLink :to="`/donationForm/${item.id}`" class="text">
            <span class="mainText"> Blood donation form for {{ item.first_name }} {{ item.second_name }}</span>
            <span class="normalText"> Gender:{{ item.gender }}</span>
            <span class="normalText">Blood type: {{ item.blood_type }}</span>
            <span class="normalText">Passed: 7</span>
            <span class="normalText">Failed: 3</span>
            <span class="normalText">Advice: Accept</span>
        </NuxtLink>

        <div class="bottom">
            <button type="submit" @click="set_appointment" class="normal">
                Accept request
            </button>
            <button type="submit" @click="cancel_request" class="normal">
                Reject request
            </button>
        </div>

        <DoctorSetAppointment v-if="showSetAppointment"></DoctorSetAppointment>    
        <DoctorCancelRequest v-if="showCancelRequest"></DoctorCancelRequest>  
    </div>

</template>

<script setup>
const props = defineProps({
    item:{
        type:Object,
        required: true, 
    }        
});

const showSetAppointment = ref(false)
const showCancelRequest = ref(false)

const set_appointment = () =>{
    showSetAppointment.value = true
}

const cancel_request = () =>{
    showCancelRequest.value = true
}


</script>

<style scoped>
.full{
    width: 49%;
    height: 300px;
    display: flex;
    flex-direction: column;
    /* background-color: brown; */
    margin-bottom: 10px;
    border: 2px solid var(--vt-nawe-outline);
    border-radius: 20px;
    padding-left: 10px;
    padding-right: 10px;
    padding-top: 5px;
    padding-bottom: 5px;
}
.bottom{
    z-index: 1;
    display: flex;
    justify-content: space-between;
    width: 100%;
    
    /* background-color: brown; */
}
.normal{
    margin-right: 5px;
    margin-left: 5px;

}
.text{
    height: 80%;
    display: flex;
    flex-direction: column;
}
</style>