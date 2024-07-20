<template>
    <div class="hold">
        <div class="warning" >
            <span class="buttonText warning_badge">Prototype</span>            
        </div>

        <div class="container" >
            <div>
                <img src="@/assets/images/logo-no-background.png" alt="">
            </div>
            <div>
                <NuxtLink to="/documentation" class="secondary_button" > 
                    <span class="normalText">documentation</span>
                </NuxtLink>
                <NuxtLink to="/documentation" class="secondary_button" > 
                    <span class="normalText">Contact</span>
                </NuxtLink>
                <NuxtLink to="/about" class="secondary_button" > 
                    <span class="normalText">about</span>
                </NuxtLink>
                <NuxtLink to="/donor" class="primary_button" > 
                    <span class="buttonText" > Donor</span>
                </NuxtLink>
                <NuxtLink to="/nurse" class="primary_button" > 
                    <span class="buttonText" > Nurses</span>
                </NuxtLink>
                <NuxtLink to="/doctor" class="primary_button" > 
                    <span class="buttonText" > Doctor</span>
                </NuxtLink>
                <NuxtLink to="/management" class="primary_button" > 
                    <span class="buttonText" > Management</span>
                </NuxtLink>

            </div>
        </div>
    </div>
</template>

<script setup>
</script>

<style scoped>
.hold {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: auto;
    width: 100%;
    background-color: white;
    /* background-color: #F2F2F2;     */
}
.warning{
    background-color: white;
    width: 100%;
    height: 40px;
    display: flex;
    /* justify-content: center; */
    align-items: center;
}
.warning_badge {
  background-color: rgb(255, 196, 196);
  color: black;
  margin: 20px;
  padding: 5px;
  border-radius: 20px;
  position: relative; /* Ensure pseudo-element is positioned relative to the parent */
  z-index: 1;
}

.warning_badge::before {
  content: "";
  position: absolute;
  top: -2px;
  left: -2px;
  right: -2px;
  bottom: -2px;
  border-radius: 20px;
  background: linear-gradient(45deg, red, yellow, red);
  z-index: -1; /* Ensure the pseudo-element is behind the text */
}

.warning_badge > * {
  position: relative;
  z-index: 1;
}
.container{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 70px;
    /* background-color: brown; */
}
img{
    width: auto;
    height: 50px;
}
</style>