<template>
    <BackButton></BackButton>
    <div class="holder">
        <div class="container">
            <span class="normalText"> {{ form }}</span>
            <span class="normalText" > Name: {{ form.first_name }} {{ form.second_name }}</span>
            <span class="normalText" ></span>
            <div class="bottom">
                <button type="submit" @click="set_appointment" class="normal">
                    Accept request
                </button>
                <button type="submit" @click="cancel_request" class="normal">
                    Reject request
                </button>
            </div>
        </div>

    <DoctorSetAppointment v-if="showSetAppointment"></DoctorSetAppointment>    
    <DoctorCancelRequest v-if="showCancelRequest"></DoctorCancelRequest>    
    </div>

</template>

<script setup>
const form = ref([])
const route = useRoute();

const showSetAppointment = ref(false)
const showCancelRequest = ref(false)

const set_appointment = () =>{
    showSetAppointment.value = true
}

const cancel_request = () =>{
    showCancelRequest.value = true
}

const get_donation_form = async () => {
    try {
        const pk = route.params.id; // Get the `id` parameter from the route
        console.log('the id is', pk)
        const response = await fetch(`http://127.0.0.1:8000/api/v1/donation/form/${pk}`, {
            method: 'GET',
            headers: {
                'Content-Type': 'application/json'
            }
        });

        if (!response.ok) {
            throw new Error(`Error fetching donation form: ${response.statusText}`);
        }

        const data = await response.json();
        form.value = data
        console.log(data);
        // Process the data as needed
    } catch (error) {
        console.error("Error:", error);
    }
};

// Call the function, or call it on mounted if needed
onMounted(() => {
    get_donation_form();
});
</script>

<style scoped>
.bottom{
    z-index: 1;
    display: flex;
    justify-content: space-between;
    width: 100%;
    
    /* background-color: brown; */
}
.container{
    flex-direction: column;
}
.normal{
    margin-right: 5px;
    margin-left: 5px;

}
</style>