<script setup>
import Btns from "./Btns.vue";
import { fadeUpAttrs, fadeLeftAttrs } from "@/utils/fade.js";
import img1 from "@/assets/imgs/solo.jpg";
import img2 from "@/assets/imgs/two.jpg";
import img4 from "@/assets/imgs/four.jpg";
import img5 from "@/assets/imgs/all.jpg";

const cards = [
	{
		title: "Solo Set",
		content:
			"A carefully crafted pasta dish by our chef, served with today's soup and garlic bread, plus a drink — perfect for enjoying a hearty meal on your own.",
		img: img1,
	},
	{
		title: "Duo Set",
		content:
			"Choose any two pasta dishes with a shared appetizer, two drinks, and dessert — ideal for couples or friends to enjoy a relaxed lunch or romantic dinner.",
		img: img2,
	},
	{
		title: "Family Set (For Four)",
		content:
			"Four pasta selections with a fresh salad, two desserts, and a jug of fruit drink served with a crispy platter — a great choice for family or group gatherings.",
		img: img4,
	},
	{
		title: "Private Event",
		content:
			"A tailored experience for celebrations, parties, or company events — with a customizable menu, drinks, and dedicated space to create memorable moments for every guest.",
		img: img5,
	},
];
</script>

<template>
	<section v-bind="fadeLeftAttrs" 
        data-aos-duration="400" 
        class="mx-4 md:mx-10 lg:mx-40 my-36">
		<h2 class="text-center md:text-left text-3xl font-bold text-zinc-50 mb-2">Our Signature Sets</h2>
		<p class="w-full xl:w-1/2 text-xl text-center md:text-left text-zinc-400 font-bold">
			From solo treats to family feasts, our thoughtfully crafted pasta sets offer something
			for every occasion. Whether you’re here for a quick bite or a big celebration, we’ll
			make it a delicious and memorable experience.
		</p>
	</section>

	<div class="grid grid-cols-4 gap-x-0 gap-y-4 sm:gap-x-4 mx-4 md:mx-10 xl:mx-40 mb-18 md:mb-36 text-zinc-950 bg-repeat">
		<div v-for="(card, index) in cards" :key="index" v-bind="fadeUpAttrs" 
            :data-aos-duration="(index + 1) * 200" 
			class="col-span-4 sm:col-span-2 xl:col-span-1 px-0 bg-zinc-700 text-zinc-50 rounded-xl overflow-hidden">
			<img :src="card.img" alt="food set image" class="hover:scale-105 duration-400" />
			<h3 class="my-6 text-2xl font-bold text-center">{{ card.title }}</h3>
			<p class="my-6 px-10">{{ card.content }}</p>
		</div>
		<div v-bind="fadeUpAttrs" data-aos-delay="800" 
            class="col-span-4 mt-10 text-center">
			<Btns text="learn more" class="py-1 md:py-3 px-12 md:px-20" />
		</div>
	</div>
</template>

<style scoped>
.card-shadow {
    box-shadow: rgba(14, 30, 37, 0.12) 0px 2px 4px 0px, rgba(14, 30, 37, 0.32) 0px 2px 16px 0px;
}
</style>
