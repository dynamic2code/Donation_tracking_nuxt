<template>
    <div class="feature" @click="isOpen = true">
        <div class="image_raw" >
            <div class="image" :style="{ backgroundColor: randomBackgroundColor }">
                <UIcon :name="feature.icon" dynamic :style="{ color: 'white' }" />
            </div>
        </div>
        <div class="text">
            <span class="largeText">{{ feature.heading }}</span>
            <span class="normalText">{{ feature.text }}</span>
        </div>
    </div>

    <USlideover v-model="isOpen">
      <div class="p-4 flex-1 bg-white">
        <UButton
          color="white"
          variant="ghost"
          size="sm"
          icon="i-heroicons-x-mark-20-solid"
          class="flex sm:hidden absolute end-5 top-5 z-10"
          square
          padded
          @click="isOpen = false"
        />
        <div class="info">
            <div class="top">
                <span class="largeText">{{feature.heading}}</span>
            </div>
            <span class="normalText">
                {{feature.explanation}}
            </span>
        </div>
      </div>
    </USlideover>
</template>

<script setup>
const props = defineProps({
  feature: {
    type: Object,
    required: true,
    default: () => ({
      image: '',
      heading: '',
      text: '',
    })
  }
})

const isOpen = ref(false)

// Function to generate a random color
const generateRandomColor = () => {
  const letters = '0123456789ABCDEF';
  let color = '#';
  for (let i = 0; i < 6; i++) {
    color += letters[Math.floor(Math.random() * 16)];
  }
  return color;
};

const randomBackgroundColor = ref('');

onMounted(() => {
  randomBackgroundColor.value = generateRandomColor();
});
</script>

<style scoped>
.feature{
    display: flex;
    width: 90%;
    /* background-color: aquamarine; */
    margin: 5px;
    cursor: pointer;
}
.image_raw{
    width: 30%;
    margin-right: 5px;
    /* background-color: blue; */
}
.image{
    width: 50px;
    height: 50px;
    padding: 5px;
    border-radius: 10px;
    display: flex;
    justify-content: center;
    align-items: center;

}
.image img{
    width: 30px;
}
.text{
    display: flex;
    flex-direction: column;
}
.info{
    width: 100%;
    height: 100%
}
.top{
    margin-bottom: 20px;
}
</style>