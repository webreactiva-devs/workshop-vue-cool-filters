<template>
 <div :style="`background-color: aqua; width: ${size}px; height: ${size}px`">
	Mi primer compoenente
 </div>
</template>

<script setup>
const props =  defineProps(['size'])
</script>