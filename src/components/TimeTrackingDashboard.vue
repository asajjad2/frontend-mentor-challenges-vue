<template>
    <div class="min-h-screen max-w-screen flex justify-center items-center bg-[#0f1424] text-white">
        <div class="flex gap-4">
            <ProfileCard :img="Avatar" name="Jeremy Robson" :timeframe="timeframe" @update-timeframe="handleTimeframeUpdate"/>
            <div class="times grid grid-cols-3 gap-4">
                <TimeCard v-for="(item, index) in jsonData" :item="item" :key="item.title" :color="getColor(index)" :timeframe="timeframe" :icon="getIcon(index)"/>
            </div>
        </div>
    </div>
</template>

<script setup>

    import Work from '@/assets/icon-work.svg';
    import Play from '@/assets/icon-play.svg';
    import Study from '@/assets/icon-study.svg';
    import Exercise from '@/assets/icon-exercise.svg' 
    import Social from '@/assets/icon-social.svg'
    import SelfCare from '@/assets/icon-self-care.svg'
    import Avatar from '@/assets/image-jeremy.png'

    import TimeCard from './TimeCard.vue';
    import ProfileCard from './ProfileCard.vue';

    import jsonData from '@/assets/timetracking-data.json'
    
    import { ref } from 'vue';

    const timeframe = ref('weekly');
    const colors = ["#ff8c66", "#56c2e6", "#ff5c7c", "#4acf81", "#7536d3", "#f1c65b"]
    const getColor = (index) => {
        return colors[index];
    }

    const icons = [Work, Play, Study, Exercise, Social, SelfCare];
    const getIcon = (index) => {
        return icons[index];
    }

    const handleTimeframeUpdate = (newTimeFrame) => timeframe.value = newTimeFrame;

    </script>

<!-- 
    lightred- #ff8c66
    softblue- #56c2e6
    lightred- #ff5c7c
    limegreen- #4acf81
    violet- #7536d3
    selforange- #f1c65b
    vdarkblue- #0f1424
    darkblue- #1c1f4a
    purple- #6f76c8
    paleblue- #bdc1ff
 -->