<template>
    <div class="bg-[#f4d04e] text-black min-h-screen flex justify-center items-center w-screen">
        <div class="bg-white w-80 rounded-lg border border-black shadow-custom p-4 space-y-2">
            <img :src="Banner" alt="" class="rounded-lg">
            <h4 class="bg-[#f4d04e] px-2 py-1 font-semibold text-xs text-center max-w-16 ">Learning</h4>
            <h3 class="text-sm font-medium ">Published {{dateRef}}</h3>
            <h2 class="text-xl font-bold hover:text-[#f4d04e] cursor-pointer">HTML & CSS foundations</h2>
            <p class="text-gray-400 ">Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium animi incidunt unde doloribus quam distinctio voluptas necessitatibus maxime ea ducimus.</p>
            <div class="flex gap-2 pt-2">
                <img :src="Avatar" alt="" class="h-6 w-6 rounded-full bg-gray-400">
                <h3>Greg Heeper</h3>
            </div>
        </div>
    </div>
</template>


<script setup>

    import { ref } from 'vue';
    import Banner from '@/assets/illustration-article.svg';
    import Avatar from '@/assets/image-avatar.webp';

 
    // Initialize the date and format it
    const months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
    let date = new Date();
    let formattedDate = date.getDate() + " " + months[date.getMonth()] + " " + date.getFullYear();
    let dateRef = ref(formattedDate)
        
</script>