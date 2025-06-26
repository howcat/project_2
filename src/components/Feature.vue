<script setup>
import { reactive } from 'vue';
import { fadeUpAttrs, fadeRightAttrs } from "@/utils/fade.js";
import pattern from "@/assets/imgs/pattern.png";
import spaghetti from "@/assets/imgs/spaghetti.jpg";
import penne from "@/assets/imgs/penne.jpg";
import orecchiette from "@/assets/imgs/orecchiette.jpg";
import fusilli from "@/assets/imgs/fusilli.jpg";
import chifferi from "@/assets/imgs/chifferi.jpg";
import farfalle from "@/assets/imgs/farfalle.jpg";
const pasta = reactive([
	{ type: "Spaghetti", hover: false, click: false, imgUrl: spaghetti },
	{ type: "Penne", hover: false, click: false, imgUrl: penne },
	{ type: "Orecchiette", hover: false, click: false, imgUrl: orecchiette },
	{ type: "Fusilli", hover: false, click: false, imgUrl: fusilli },
	{ type: "Chifferi", hover: false, click: false, imgUrl: chifferi },
	{ type: "Farfalle", hover: false, click: false, imgUrl: farfalle },
]);

const handleHoverEnter = (item) => {
    item.hover = true
}
const handleHoverLeave = (item) => {
    item.hover = false
}
function toggleClick(item) {
    item.click = !item.click;
    pasta.forEach(p => {
        if (p !== item) {
            p.click = false; // Reset other items
        }
    });
}
</script>

<template>
    <div :style="{backgroundImage:'url(' + pattern +')'}" class="py-18 md:py-40">
        <p v-bind="fadeRightAttrs" 
            class="mx-0 lg:mx-40 px-4 lg:px-0 mb-18 md:mb-36 xl:w-1/2 md:text-xl text-center xl:text-left text-zinc-400 font-bold">
            Pasta comes in endless varieties—from classic Spaghetti and spiral Fusilli to charming
            bow-tie Farfalle—each shape offering a unique texture and flavor experience with every sauce.
        </p>
        <div class="grid grid-cols-2 xl:grid-cols-3 gap-1 justify-center mx-4 lg:mx-40">
            <div v-for="(item, index) in pasta" :key="index" v-bind="fadeUpAttrs" 
                :data-aos-duration="(index + 1) * 200" 
                :style="{ backgroundImage: `url(${item.imgUrl})` }" 
                @mouseenter="handleHoverEnter(item)" @mouseleave="handleHoverLeave(item)" 
                @click="toggleClick(item)"
                class="col-span-1 relative py-16 bg-center bg-cover text-zinc-50 cursor-pointer rounded overflow-hidden">
                <div class="absolute flex justify-center items-center inset-0 z-10 text-xl md:text-3xl xl:text-5xl font-medium">{{ item.type }}</div>
                <div class="absolute -inset-1 bg-zinc-400 duration-400 ease-out-sinc" :class="item.hover ? 'opacity-0' : 'opacity-60'"></div>
                <div class="absolute -inset-1 bg-amber-400 duration-500 ease-in-out" 
                :class="item.click ? 'translate-x-0' : '-translate-x-full translate-x-'"></div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.slide-leave-active, .slide-enter-active {
	transition: all 0.9s ease;
}
.slide-enter-from {
	transform: translateY(100%);
}
.slide-leave-to {
	transform: translateY(100%);
}
</style>