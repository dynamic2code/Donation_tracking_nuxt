<template>
    <div class="top">
        <form @submit.prevent="submitForm">
            <!-- Name Fields -->
            <div class="form-group">
                <div class="item">
                    <label for="donor_first_name" class="normalText">First Name</label>
                    <input type="text" id="donor_first_name" class="alt" v-model="first_name" placeholder="Enter your first name" required />                    
                </div>
                <div class="item">
                    <label for="donor_second_name" class="normalText">Second Name</label>
                    <input type="text" id="donor_second_name" class="alt" v-model="second_name" placeholder="Enter your second name" required />                    
                </div>
                <div class="item">
                    <label for="donor_sur_name" class="normalText">Sur Name</label>
                    <input type="text" id="donor_sur_name" class="alt" v-model="sur_name" placeholder="Enter your sur name" required />                    
                </div>
            </div>

            <!-- Contact Information -->
            <div class="form-group">
                <div class="item">
                    <label for="donor_gender" class="normalText">Gender</label>
                    <select id="donor_gender" class="alt" v-model="gender" required>
                        <option disabled value="">Select gender</option>
                        <option value="F">Female</option>
                        <option value="M">Male</option>
                    </select>
                </div>
                <div class="item">
                    <label for="email" class="normalText">Email</label>
                    <input type="email" id="email" class="alt" v-model="email" placeholder="Enter your email" required />                    
                </div>
                <div class="item">
                    <label for="phone" class="normalText">Phone</label>
                    <input type="tel" id="phone" class="alt" v-model="phone_number" placeholder="Enter your phone number" required/>
                </div>
                <div class="item">
                    <label for="donor_address" class="normalText">Address</label>
                    <input type="text" id="donor_address" class="alt" v-model="town" placeholder="Enter your town of residency"/>
                </div>
            </div>

            <!-- Additional Fields -->
            <div class="form-group">
                <div class="item">
                    <label for="date_of_birth" class="normalText">Date of Birth</label>
                    <input type="date" id="date_of_birth" class="alt" v-model="date_of_birth" :min="minDate" :max="maxDate" required/>
                </div>
                <div class="item">
                    <label for="blood_type" class="normalText">Blood Type</label>
                    <select id="blood_type" class="alt" v-model="blood_type" required>
                        <option disabled value="">Select blood type</option>
                        <option value="O+">O+</option>
                        <option value="O-">O-</option>
                        <option value="A+">A+</option>
                        <option value="A-">A-</option>
                        <option value="B+">B+</option>
                        <option value="B-">B-</option>
                        <option value="AB+">AB+</option>
                        <option value="AB-">AB-</option>
                        <option value="None">Don't know</option>
                    </select>
                </div>
                <div class="item">
                    <label for="last_donation" class="normalText">Last Donation Date</label>
                    <input type="date" id="last_donation" class="alt" v-model="last_donation"/>
                </div>
            </div>

            <button type="submit" @onClick="submitForm" class="normal">Submit</button>
        </form>

    </div>
  
</template>

<script setup>
const first_name = ref('');
const second_name = ref('');
const sur_name =ref('');
const gender = ref('');
const email = ref('');
const phone_number = ref('');
const town = ref('');
const date_of_birth = ref('');
const blood_type = ref('');
const last_donation = ref('');

const today = new Date();
const maxDate = new Date(today.getFullYear() - 16, today.getMonth(), today.getDate()).toISOString().split('T')[0];
const minDate = new Date(today.getFullYear() - 65, today.getMonth(), today.getDate()).toISOString().split('T')[0];

const config = useRuntimeConfig();
const toast = useToast()

const  submitForm = async() =>{
    console.log("clicked")
    try {
        const response = await fetch(`http://127.0.0.1:8000/api/v1/donation/form`, {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                first_name: first_name.value,
                second_name: second_name.value,
                sur_name: sur_name.value,
                gender: gender.value,
                email: email.value,
                phone_number: phone_number.value,
                town: town.value,
                date_of_birth: date_of_birth.value,
                blood_type: blood_type.value,
                last_donation: last_donation.value
            })
        })
        const data = await response.json();
        if(response.ok){
            toast.add({
                title: `Donation form for ${first_name.value} was sent successfully`,
                description: 'Thank you for your generosity. If you are eligible, you will receive a transfusion appointment via SMS.'
            });
            window.location.reload();

        }else{
            toast.add({
                title: `Error sending donation form for ${first_name.value}`,
                description: 'It is not you it is us. Please try again later.'
            });
        }

    }catch(err){
        console.error("Form submission error:", err);
        toast.add({
            title: "Network or Server Error",
            description: "Please check your connection and try again.",
            type: 'error'  // Use the error type
        });
    }
}
</script>

<style scoped>
.top {
    display: flex;
    justify-content: space-between;
    width: 98%;
    margin-bottom: 20px;
    /* background-color: blueviolet; */
}
</style>
