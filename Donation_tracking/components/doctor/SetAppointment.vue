<template>
    <div v-if="showComponent" class="holder">
        <div class="hold">
            <div class="cancel">
                <UIcon @click="close" name="i-ic:baseline-close" dynamic :style="{ color: 'black', height: '40px' }"/>
            </div>
            <div class="appointment">
                <form @submit.prevent="submitForm">
                    <div class="form-group">
                        <div class="item">
                            <label for="hospital" class="normalText">Hospital</label>
                            <input type="text" id="hospital" v-model="hospital" placeholder="Your Hospital" required />                            
                        </div>

                        <div class="item">
                            <label for="doctor" class="normalText">Doctor</label>
                            <input type="text" id="doctor" v-model="doctor" placeholder="The Staff in charge of the procedure" required />                            
                        </div>

                        <div class="item">
                            <label for="donor" class="normalText">Donor</label>
                            <input type="text" id="donor" v-model="donor" placeholder="The donor" required />                            
                        </div>

                    </div>

                    <div class="form-group">
                        <div class="item">
                            <label for="appointment_date" class="normalText">Appointment Date</label>
                            <input type="datetime-local" id="appointment_date" v-model="appointment_date" placeholder="Appointment Date" required />                            
                        </div>

                        <div class="item">
                            <label for="reason" class="normalText">Reason</label>
                            <input type="text" id="reason" v-model="reason" placeholder="Blood donation" required />                            
                        </div>                        
                    </div>

                    <button type="submit" @onClick="submitForm" class="normal">Submit</button>
                </form>
            </div>            
        </div>        
    </div>
</template>

<script setup>
import { ref } from 'vue';

const hospital = ref('');
const doctor = ref('');
const appointment_date = ref('');
const reason = ref('Blood donation');
const donor = ref('');
const status = ref('pending');

const config = useRuntimeConfig();
const toast = useToast()
// Define a ref to control visibility
const showComponent = ref(true);

// Close function to hide the component
const close = () => {
    showComponent.value = false;
};

const submitForm = async() =>{
    try {
        const response = await fetch('/api/appointments/', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify({
            hospital: hospital.value,
            doctor: doctor.value,
            appointment_date: appointment_date.value,
            reason: reason.value,
            donor: donor.value,
            status: status.value
          }),
        });

        if (response.ok) {
          toast.add({
            title: 'Appointment created successfully!',
            description: 'Your appointment has been created successfully!',
          })
          close();
        } else {
          const errorData = await response.json();
          console.error('Error:', errorData);
          toast.add({
            title: 'Error creating appointment',
            description: 'Failed to create appointment. Please try again.',
          })
        }
    } catch (error) {
        console.error('Error:', error);
        toast.add({
            title: 'Error creating appointment',
            description: 'Failed to create appointment. Please try again.',
        })
    }
}
</script>

<style scoped>
.holder{
    position: fixed;
    top: 0;
    z-index: 4;
    left: 0;
    /* background-color: aquamarine; */
    justify-content: center;
    align-items: center;
}
.hold{
    width: 800px;
    height: auto;
    padding: 2%;
    border: 2px solid var(--vt-nawe-outline);
    border-radius: 20px;
    z-index: 5;
    display: flex;
    flex-direction: column;
    /* justify-content: center; */
    align-items: center;
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
