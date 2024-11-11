<template>
    <div class="fill">
        <DoctorDonationFormOverview v-for="item in items" :item="item" ></DoctorDonationFormOverview>
    </div>


</template>

<script setup>
const items =ref([])

const get_donation_forms = async() =>{
    try{
        const response = await fetch('http://127.0.0.1:8000/api/v1/donation/form',{
            method: 'GET',
            headers: {
                'Content-Type': 'application/json',
            }
        })
        const data = await response.json()
        items.value = data

    }catch(error){
        console.log("Error")
    }
}

onMounted(() => {
    get_donation_forms();
});
</script>

<style scoped>
.fill {
    width: 100%;
    height: 100%;
    padding-left: 10px;
    padding-right: 10px;
    overflow: auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

</style>