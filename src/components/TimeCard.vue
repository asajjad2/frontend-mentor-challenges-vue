<template>
    <div :style="{ backgroundColor: color }" class="w-52 rounded-lg relative">

        <img :src="props.icon" alt="" class="absolute top-1 right-1 z-0 ">

        <div class="bg-[#1c1f4a] mt-10 rounded-lg p-4 space-y-4 z-10">
            <div class="flex justify-between">
                <h4>{{ props.item.title }}</h4>
            </div>
            <div class="space-y-2">
                <h1 class="text-4xl ">{{timeInfo.data.current}}hrs</h1>
                <p class="text-sm text-gray-400">Last {{timeInfo.word}} - {{ timeInfo.data.previous}}hrs</p>
            </div>
        </div>

    </div>
</template>

<script setup>

    import { computed } from 'vue';

    const props = defineProps(['item', 'color', 'timeframe','icon'])
    
    const timeInfo = computed(() => {

        let data;
        let word;

        switch (props.timeframe) {

            case 'daily':
            data = props.item.timeframes.daily;
            word = 'day';
            break;
            case 'weekly':
            data = props.item.timeframes.weekly;
            word = 'week';
            break;
            case 'monthly':
            data = props.item.timeframes.monthly;
            word = 'month';
            break;
            default:
            data = {}; // Default case if needed
            word = '';
        }

        return { data, word };
    });

</script>
