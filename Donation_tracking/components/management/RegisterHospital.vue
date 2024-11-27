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
                            <label for="hospital" class="normalText">Hospital Name</label>
                            <input type="text" id="name" v-model="name" placeholder="Your Hospital Name" required />                            
                        </div>

                        <div class="item">
                            <label for="doctor" class="normalText">Address</label>
                            <input type="text" id="address" v-model="address" placeholder="The Address" required />                            
                        </div>

                        <div class="item">
                            <label for="donor" class="normalText">Town</label>
                            <input type="text" id="town" v-model="town" placeholder="The nearest town" required />                            
                        </div>

                    </div>

                    <div class="form-group">
                        <div class="item">
                            <label for="appointment_date" class="normalText">Email</label>
                            <input type="email" id="email" v-model="email" placeholder="Your email" required />                            
                        </div>

                        <div class="item">
                            <label for="reason" class="normalText">Phone Number</label>
                            <input type="text" id="phone_number" v-model="phone_number" placeholder="The phone number contact (+254...)" required />                            
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

const name = ref('');
const address = ref('');
const town = ref('');
const phone_number = ref('');
const email = ref('');


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
        const response = await fetch('http://127.0.0.1:8000/api/v1/hospital/', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json',
          },
          body: JSON.stringify({
            name: name.value,
            address: address.value,
            town: town.value,
            phone_number: phone_number.value,
            email: email.value
          }),
        });

        if (response.ok) {
          toast.add({
            title: 'Hospital created successfully!',
            description: 'Your Hospital has been created successfully!',
          })
          close();
        } else {
          const errorData = await response.json();
          console.error('Error:', errorData);
          toast.add({
            title: 'Error creating appointment',
            description: 'Failed to create the hospital account. Please try again.',
          })
        }
    } catch (error) {
        console.error('Error:', error);
        toast.add({
            title: 'Error creating appointment',
            description: 'Failed to create the hospital account . Please try again.',
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
    background-color: rgba(0, 0, 0, 0.6);
    justify-content: center;
    align-items: center;
}
.hold{
    width: 800px;
    height: auto;
    padding: 2%;
    border: 2px solid var(--vt-nawe-outline);
    background-color: var(--vt-nawe-white);
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
