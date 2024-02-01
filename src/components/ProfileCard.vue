<template>
    <div class="bg-[#1c1f4a] w-52 rounded-b-lg">
        <div class="bg-violet-600 p-4 space-y-4 pb-12 rounded-lg">
            <img :src="props.img" alt="" class="w-14 h-14 rounded-full border-2 border-white">
            <div>
                <h3 class="text-gray-300 text-sm">Report for</h3>
                <h1 class="text-4xl">{{ props.name }}</h1>
            </div>
        </div>
        <div class="p-4 space-y-2">
            <h2 :class="props.timeframe==='daily'?'text-white':'text-gray-400' + ' text-sm cursor-pointer'"
                @click="$emit('update-timeframe', 'daily')"
            >Daily</h2>
            <h2 :class="props.timeframe==='weekly'?'text-white':'text-gray-400' + ' text-sm cursor-pointer'"
                @click="$emit('update-timeframe', 'weekly')"
            >Weekly</h2>
            <h2 :class="props.timeframe==='monthly'?'text-white':'text-gray-400' + ' text-sm cursor-pointer'"
                @click="$emit('update-timeframe', 'monthly')"
            >Monthly</h2>
        </div>
    </div>
</template>

<script setup>
    const props = defineProps(['img', 'name', 'timeframe'])

</script>