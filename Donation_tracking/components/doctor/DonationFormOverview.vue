<template>
    <div class="full" >
        <NuxtLink :to="`/donationForm/${item.id}`" class="text">
            <span class="mainText"> Blood donation form for {{ item.first_name }} {{ item.second_name }}</span>
            <div class="item_holder">
                <div class="item" >
                    <span class="smallText">Blood type:</span>
                    <span class="normalText">{{ item.blood_type }}</span>
                </div>

                <div class="item" >
                    <span class="smallText">Gender:</span>
                    <span class="normalText">{{ item.gender }}</span>
                </div>

                <div class="item" >
                    <span class="smallText">Year of birth:</span>
                    <span class="normalText">{{ item.date_of_birth}}</span>
                </div>

                <div class="item" >
                    <span class="smallText">Last donation:</span>
                    <span class="normalText">{{ item.last_donation }}</span>
                </div>    
                <div class="item" >
                    <span class="smallText">Blood type:</span>
                    <span class="normalText">{{ item.blood_type }}</span>
                </div>

                <div class="item" >
                    <span class="smallText">Gender:</span>
                    <span class="normalText">{{ item.gender }}</span>
                </div>

                <div class="item" >
                    <span class="smallText">Year of birth:</span>
                    <span class="normalText">{{ item.date_of_birth}}</span>
                </div>

                <div class="item" >
                    <span class="smallText">Last donation:</span>
                    <span class="normalText">{{ item.last_donation }}</span>
                </div>
            </div>

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

const colors = ['#e2fde8', '#d9f7fa', '#faead6'];

const set_background = () => {
    const elements = document.getElementsByClassName('full');
    for (let i = 0; i < elements.length; i++) {
        elements[i].style.backgroundColor = colors[i % colors.length];
    }
};

onMounted(() => {
    set_background();
});

</script>

<style scoped>
.full{
    width: 49%;
    height: 300px;
    display: flex;
    flex-direction: column;
    /* background-color: brown; */
    margin-bottom: 10px;
    /* border: 2px solid var(--vt-nawe-outline); */
    /* background-color: var(--vt-nawe-light-green); */
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
.item{

}
.item_holder{
    display: flex;
    flex-wrap: wrap; 
}
</style>