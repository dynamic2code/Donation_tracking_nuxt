<template>
    <div class="for_all">
        <div class="header">
            <span class="largeText" >Component</span>
        </div>
        <div class="interaction">
            <UInput
                icon="i-heroicons-magnifying-glass-20-solid"
                size="sm"
                color="gray"
                :trailing="false"
                placeholder="Search..."
                :style="{ backgroundColor: 'white' }"
            />

            <div class="boundary">
                <UIcon name="i-tabler:inbox" dynamic :style="{ color: 'black' }"/>
            </div>

            <div class="boundary">
                <UIcon name="i-tabler:bell" dynamic :style="{ color: 'black' }"/>
            </div>

            <div class="boundary">
                <UIcon name="i-tabler:user-plus" dynamic :style="{ color: 'black' }"/>
                <span class="mainText"> invite</span>
            </div>
        </div>
    </div>
    <hr class="line">
    <div class="hey">
        <div class="name">
            <span class="lText">Hey stranger</span>
        </div>
        <div>
            <UPopover :popper="{ placement: 'bottom-start' }">
                <UButton icon="i-heroicons-calendar-days-20-solid" :label="format(date, 'd MMM, yyy')" 
                :style="{ backgroundColor: 'white'}"
                class="boundary" />

                <template #panel="{ close }">
                <DatePicker v-model="date" is-required @close="close" />
                </template>
            </UPopover>
        </div>
    </div>
</template>

<script setup>
import { format } from 'date-fns'

const date = ref(new Date())
</script>

<style scoped>
.for_all{
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.header{
    /* background-color: blue; */
    /* width: 20%; */
    padding-left: 20px;
    /* padding-right: 10px; */
}
.interaction{
    display: flex;
    align-items: center;
}

.boundary{
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 10px;
    border-radius: 10px;
    border: 1px solid var(--vt-nawe-outline);
    padding: 10px;
}

.line{
    width: 100%;
    color: #F2F2F2;
}
.hey{
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-left: 30px;
    padding-right: 30px;
    /* background-color: blueviolet; */
}
</style>