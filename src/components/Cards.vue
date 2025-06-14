<script setup>
import img1 from "@/assets/solo.jpg";
import img2 from "@/assets/two.jpg";
import img4 from "@/assets/four.jpg";
import pattern from "@/assets/pattern.png";

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
];
</script>

<template>
	<div :style="{backgroundImage:'url(' + pattern +')'}" class="grid grid-cols-3 gap-0 xl:gap-12 my-18 md:my-36 py-2 md:py-8 px-4 md:px-10 xl:px-40 text-amber-50  bg-repeat">
		<div v-for="(card, index) in cards" :key="index" class="col-span-3 lg:col-span-1 h-auto px-0 md:px-10 rounded">
			<h3 class="my-6 text-2xl text-center">{{ card.title }}</h3>
			<img :src="card.img" alt=".." />
			<p class="my-6">{{ card.content }}</p>
		</div>
	</div>
</template>

<style scoped>
</style>
