<template>
    <div class="halves">
        <div class="first">
            <div class="head">
                <span class="xlText" >Simplifying & Streamlining The Health Industry</span>
                <span class="normalText">This is a project whose goal is to make the procedure and communication in a hospital setting are more efficient. We also intend to include the management aspect to the system. </span>
                <div class="progress">
                    <span class="largeText">The projects process</span>
                    <UProgress 
                    :value="20"
                    indicator
                    color="blue"
                    />
                </div>
                <div class="contributors">
                    <span class="largeText">Contributors</span>
                    <a href="https://github.com/dynamic2code">
                        <UAvatar
                            size="xl"
                            src="https://avatars.githubusercontent.com/u/83699448?s=400&u=9234ecce58cdff27b908ad09a964262725e319c8&v=4"
                            alt="Avatar"
                            :style="{border: '1px solid black'}"
                        />
                    </a>
                    
                </div>
            </div>
        </div>
        <div class="second">
            <div class="features">
                <FeatureComponent v-for="feature in features" :key="index" :feature="feature"></FeatureComponent>
            </div>
        </div>
    </div>
</template>

<script setup>
const features = [
  {
    icon: 'i-tabler-heart-handshake',
    heading: 'Blood Donation',
    text: 'Click to see how we are making blood donation, blood drives, and donor messaging easier',
    explanation: 'Our platform streamlines the blood donation process in several key ways. First, we collect necessary information from potential donors through a detailed form, which is then presented to a doctor for review. The doctor can approve or disapprove the donation directly within our system, and the donor is promptly notified of their appointment status. We also track the blood stored in blood banks and facilitate the matching of compatible blood types between different hospitals, making it easier to find the right blood for patients in need. Additionally, we maintain an up-to-date database of donor contact information for quick access during emergencies. We believe in celebrating the impact of our donors, so we send personalized messages to donors when their blood is used to save a life. Our platform also helps track blood shortages and communicate effectively about upcoming blood drives, ensuring that donors are well-informed and engaged.'
  },
  {
    icon: 'i-tabler:pig-money',
    heading: 'Money Donation',
    text: 'Click to see how we are making money donation direct to the patients bill possible',
    explanation: 'We aim to make financial contributions as transparent and effective as possible. Our system allows donors to contribute directly to patients\' medical bills, ensuring that their generosity has an immediate and meaningful impact. To prevent fraud and build trust, all donations are verified with proof of legitimacy from the hospitals receiving the funds. This verification process ensures that donations are used appropriately and reach those who truly need them.'
  },
  {
    icon: 'i-tabler:building-hospital',
    heading: 'Hospital Staff',
    text: 'Click to see how we are making hospital staff management easier',
    explanation: 'Managing hospital staff is a complex task, and our platform is designed to simplify this process. We provide tools for easy duty allocation, ensuring that staff schedules are efficiently managed and that the right personnel are assigned to the right tasks. Our task follow-up features help supervisors track the progress of various assignments, making sure that nothing falls through the cracks. Communication among staff members is streamlined through our platform, promoting better collaboration and information sharing. Additionally, our AI-assisted prescription feature supports medical staff in making accurate and timely decisions, enhancing the overall quality of care provided to patients.'
  },
  {
    icon: 'i-tabler:timeline-event-text',
    heading: 'Inventory Tracking',
    text: 'Click to see how we are making hospital inventory management possible online',
    explanation: 'Effective inventory management is crucial for hospital operations, and our platform offers comprehensive solutions to meet this need. We enable hospitals to track their inventory levels in real-time, ensuring that supplies are always available when needed. Our system also facilitates communication about inventory shortages, allowing hospitals to address these issues promptly and avoid disruptions in patient care. By providing a clear overview of inventory status, we help hospitals manage their resources more efficiently and make informed decisions about supply procurement and distribution.'
  }
];

</script>

<style scoped>

.head{
    display: flex;
    flex-direction: column;
}
.head >*{
    margin-bottom: 20px;
}
.progress{
    width: 80%;
}
.contributors{
    display: flex;
    flex-direction: column;
}
.halves{
    display: flex;
    height: 80vh;
}
.first{
    width: 60%;
    padding-top: 50px;
}
.second{
    width: 40%;
}
.image{
    margin: 20px;
    width: 100%;
    height: 100%;
    overflow: hidden;
    background-color: rgb(255, 255, 255);
    border-top-right-radius: 50px;
    border-bottom-left-radius: 50px;
}
.image img{
    display: block;
    width: 100%;
    height: auto;
    border-top-right-radius: 50px;
    border-bottom-left-radius: 50px;
}
.features {
    display: flex;
    flex-direction: column;
  /* gap: 20px; */
}
</style>
