<script setup>
import Btns from "./Btns.vue";
import Cards from "./Cards.vue";
import Feature from "./Feature.vue";
import FooterBlock from "./Footer.vue";
import { fadeDownAttrs } from "@/utils/fade.js";
import mainImage from "@/assets/imgs/main.jpg";
</script>

<template>
    <div class="w-full">
        <div class="overflow-hidden relative h-[40rem] md:h-[100vh]">
            <img :src="mainImage" alt="main" class="w-full h-full object-cover object-[50%_10%]"/>
            <Btns text="START" v-bind="fadeDownAttrs" 
                data-aos-duration="2000" data-aos-offset="0"
                class="absolute left-[50%] top-[80%] -translate-x-1/2 -translate-y-1/2 py-1 md:py-3 px-12 md:px-20" />
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
