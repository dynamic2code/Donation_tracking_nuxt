<template>
    <div class="top">
        <div>
            <AreaChart :data="data" index="name" :categories="['total', 'predicted']" />
        </div>

        <div>

        </div>

        <div>

        </div>
    </div>

</template>
<script setup lang="ts">
import AreaChart from '@/components/ui/chart-area/AreaChart.vue'

const data = [
  { name: 'Jan', total: Math.floor(Math.random() * 2000) + 500, predicted: Math.floor(Math.random() * 2000) + 500 },
  { name: 'Feb', total: Math.floor(Math.random() * 2000) + 500, predicted: Math.floor(Math.random() * 2000) + 500 },
  { name: 'Mar', total: Math.floor(Math.random() * 2000) + 500, predicted: Math.floor(Math.random() * 2000) + 500 },
  { name: 'Apr', total: Math.floor(Math.random() * 2000) + 500, predicted: Math.floor(Math.random() * 2000) + 500 },
  { name: 'May', total: Math.floor(Math.random() * 2000) + 500, predicted: Math.floor(Math.random() * 2000) + 500 },
  { name: 'Jun', total: Math.floor(Math.random() * 2000) + 500, predicted: Math.floor(Math.random() * 2000) + 500 },
  { name: 'Jul', total: Math.floor(Math.random() * 2000) + 500, predicted: Math.floor(Math.random() * 2000) + 500 },
]
</script>

<style scoped>
.top {
    display: flex;
    justify-content: space-between;
    width: 98%;
}
.top >*{
    width: 33%;
    border: 1px solid var(--vt-nawe-outline) ;   
    border-radius: 10px;
    height: 200px;
    /* background-color: black */
}
</style>
