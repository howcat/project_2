<script setup>
import Cards from "./Cards.vue";
import Feature from "./Feature.vue";
import FooterBlock from "./Footer.vue";
import mainImage from "@/assets/main.jpg";
</script>

<template>
    <div class="content w-full">
        <div class="overflow-hidden relative h-[15rem] md:h-[40rem]">
            <img :src="mainImage" alt="main" class="w-full h-full object-cover object-[50%_95%]"/>
            <button class="absolute left-[50%] top-[60%] md:top-[90%] -translate-x-1/2 -translate-y-1/2 
                bg-transparent text-amber-50 py-1 md:py-3 px-12 md:px-20 font-bold rounded border-4 border-amber-50 duration-200
                hover:bg-amber-300 hover:border-amber-300 hover:border-2 hover:text-zinc-950">
            START
            </button>
        </div>
        <div class="">
            <Feature />
            <Cards />
        </div>
        <FooterBlock />
    </div>
</template>

<style scoped>
</style>
