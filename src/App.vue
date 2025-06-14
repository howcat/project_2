<script setup>
import Navbar from "./components/Navbar.vue";
import Intro from "./components/Intro.vue";
</script>

<template>
	<header>
        <Navbar />
	</header>

	<main>
        <Intro />
	</main>
</template>

<style scoped>
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
