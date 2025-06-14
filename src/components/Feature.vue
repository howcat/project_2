<script setup>
import { reactive } from 'vue';
const pasta = reactive([
	{ type: "Spaghetti", hover: false },
	{ type: "Penne", hover: false },
	{ type: "Conchiglie", hover: false },
	{ type: "Fusilli", hover: false },
	{ type: "Chiferri", hover: false },
	{ type: "Farfalle", hover: false },
]);

const handleHoverEnter = (item) => {
    item.hover = true
}
const handleHoverLeave = (item) => {
    item.hover = false
}
</script>

<template>
    <!-- <h2 class=""></h2> -->
	<div class="my-18 md:my-36 px-4 md:px-10 lg:px-40 w-full xl:w-3/4 text-xl text-center xl:text-left font-bold">
		Pasta comes in endless varieties—from classic Spaghetti and spiral Fusilli to charming
		bow-tie Farfalle—each shape offering a unique texture and flavor experience with every
		sauce.
	</div>
	<div class="grid grid-cols-3 gap-1 justify-center mx-4 lg:mx-40">
		<div
			v-for="(item, index) in pasta" :key="index"
            @mouseenter="handleHoverEnter(item)" @mouseleave="handleHoverLeave(item)" 
			class="relative py-16 bg-zinc-700 text-zinc-50 cursor-pointer rounded overflow-hidden">
            <div class="absolute flex justify-center items-center inset-0 z-10 text-xl md:text-3xl xl:text-5xl font-medium hover:text-zinc-950 duration-600 ease-in-out">{{ item.type }}</div>
			<div class="absolute -inset-1 bg-amber-400 transition-transform duration-500 ease-in-out" 
            :class="item.hover ? 'translate-x-0' : '-translate-x-full translate-x-'"></div>
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
