<script setup>
const props = defineProps({
text: {
    type: String,
    required: true,
},
})
const emit = defineEmits(['click']);
</script>

<template>
	<button
        @click="$emit('click')" 
        class="bg-transparent text-amber-50 font-bold rounded border-2 border-amber-50 cursor-pointer duration-200 
        hover:bg-zinc-50 hover:text-zinc-950">
		{{ props.text }}
	</button>
</template>

<style scoped>
</style>
