<script setup>
import { ref } from 'vue'
import { fadeDownAttrs } from "@/utils/fade.js";
const title = "Verapamil";
const buttons = ["menu", "news", "about", "login"];
const showMenu = ref(false);
function toggleHamburger() {
    showMenu.value = !showMenu.value;
}
</script>

<template>
	<div v-bind="fadeDownAttrs" 
        data-aos-duration="400" data-aos-offset="0"
        class="xl:fixed left-0 top-0 z-10 flex justify-between items-center px-8 lg:px-20 w-full h-20 md:h-36 bg-transparent text-amber-50">
		<h1 class="text-4xl ml-0 sm:ml-4 xl:ml-16">{{ title }}</h1>
		<div class="hidden sm:flex justify-center w-auto bg-transparent py-2">
			<button
				v-for="(item, index) in buttons"
				:key="index"
				class="bg-transparent text-amber-50 font-bold mx-1 lg:mx-6 py-3 px-6 cursor-pointer rounded-full duration-300 hover:text-amber-300">
				{{ item }}
			</button>
		</div>
		<button class="sm:hidden" @click="toggleHamburger()">
			<svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					stroke-width="2"
					d="M4 6h16M4 12h16M4 18h16" />
			</svg>
		</button>
	</div>
    
	<transition name="menu-slide-fade">
        <div v-if="showMenu" class="sm:hidden absolute top-20 right-0 flex flex-col w-full z-10 leading-8 bg-zinc-600 cursor-pointer 
            transition-transform duration-500 ease-in-out">
            <button v-for="(item, index) in buttons" :key="'mobile-' + index"
                class="px-4 py-2 rounded text-zinc-50 text-center duration-500 hover:bg-zinc-800">
                {{ item }}
            </button>
        </div>
    </transition>
</template>

<style scoped>
/* 進場前狀態 */
.menu-slide-fade-enter-from {
	opacity: 0;
	transform: translateY(-10px);
}
/* 離場最後狀態 */
.menu-slide-fade-leave-to {
	opacity: 0;
	transform: translateY(-10px);
}
/* 過渡中 */
.menu-slide-fade-enter-active,
.menu-slide-fade-leave-active {
	transition: opacity 0.3s ease, transform 0.3s ease;
}
</style>
