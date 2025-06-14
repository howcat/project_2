<script setup>
import { ref } from 'vue'
const title = "Verapamil";
const buttons = ["home", "news", "about", "login"];
const showMenu = ref(false);
</script>

<template>
	<div class="flex justify-between items-center px-8 lg:px-20 w-full h-20 md:h-36 bg-transparent text-amber-50">
		<h1 class="text-4xl ml-0 lg:ml-16">{{ title }}</h1>
		<div class="hidden md:flex justify-center w-auto bg-transparent py-2">
			<button
				v-for="(item, index) in buttons"
				:key="index"
				class="bg-transparent text-amber-50 font-bold mx-1 lg:mx-6 py-3 px-6 rounded-full duration-300 hover:bg-amber-300 hover:text-zinc-950">
				{{ item }}
			</button>
		</div>
		<button class="md:hidden" @click="showMenu = !showMenu">
			<svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M4 6h16M4 12h16M4 18h16" />
			</svg>
		</button>
	</div>
	<div v-if="showMenu" class="md:hidden flex flex-col space-y-2 px-6 py-4 bg-zinc-800">
		<button v-for="(item, index) in buttons" :key="'mobile-' + index"
			class="px-4 py-2 rounded duration-200 text-zinc-50 text-center hover:bg-amber-300 hover:text-zinc-950">
			{{ item }}
		</button>
	</div>
</template>

<style scoped>
</style>
