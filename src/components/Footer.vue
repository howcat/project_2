<script setup>
import TWicon from '@/components/icons/twitter.vue';
import FBicon from '@/components/icons/facebook.vue';
import YTicon from '@/components/icons/youtube.vue';
import IGicon from '@/components/icons/instagram.vue';

const icons = [
    {svg: FBicon, link: "https://www.facebook.com/"}, 
    {svg: IGicon, link: "https://www.instagram.com/"}, 
    {svg: TWicon, link: "https://x.com/home"}, 
    {svg: YTicon, link: "https://www.youtube.com/"}];
</script>

<template>
    <div class="grid grid-cols-4 gap-4 justify-center items-center py-10 h-[20rem] bg-zinc-800 text-center">
        <div class="col-span-4">Phone: +1 (555) 123-4567</div>
        <div class="col-span-4">Email: pasta@gmail.com</div>
        <div class="col-span-4">Address: 123 Roma Street, Little Italy District, San Vito, CA 90210, USA</div>
        <div class="col-span-4 justify-center flex">
            <template v-for="(icon, index) in icons" :key="index">
                <a :href="icon.link" target="_blank">
                    <component :is="icon.svg" class="mx-2 h-8 w-8" />
                </a>
            </template>
        </div>
    </div>
</template>

<style scoped>
</style>
