<script setup>
import "aos/dist/aos.css";
import AOS from "aos";
import Navbar from "./components/Navbar.vue";
import { onMounted, ref } from "vue";

const isLoaded = ref(false);
onMounted(() => {   
	setTimeout(() => {
		isLoaded.value = true;
	}, 1600);
    AOS.init({
        once: true, 
        disable: function () {
            return window.innerWidth < 1024;
        },
    });
});

</script>

<template>
	<!-- Preloader -->
    <Transition name="fade">
        <div v-if="!isLoaded" class="preloader fixed top-0 left-0 w-screen h-screen bg-zinc-950 flex items-center justify-center z-50">
            <div class="animate-spin border-4 border-t-zinc-50 border-r-transparent border-b-zinc-50 border-l-transparent w-16 h-16 rounded-full"></div>
        </div>
    </Transition>
    
	<Navbar v-if="isLoaded" />
	<RouterView v-if="isLoaded" />
</template>

<style scoped>
.fade-enter-active, .fade-leave-active {
    transition: opacity 0.5s ease;
}
.fade-enter-from, .fade-leave-to {
    opacity: 0;
}

header {
	line-height: 1.5;
}

@media (min-width: 1024px) {
	header {
		display: flex;
		place-items: center;
		justify-content: center;
		width: 100%;
	}
}
</style>
