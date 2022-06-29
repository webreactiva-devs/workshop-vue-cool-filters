<template>
  <img :src="imgSrc" :style="imgStyle" />
  <hr />
  <button @click="changeImage">Cambiar imagen</button>
  <input type="color" v-model="borderColor" />
  <hr />
  <label for="grayscaleFilter">Escala de gris</label>
  <input type="range" v-model="grayscaleFilter" min="0" max="100" step="1" />
  <hr />
</template>

<script setup>
import { ref, computed } from "vue";

const borderColor = ref("#FF0000");
const grayscaleFilter = ref(0);
const imgSrc = ref("https://source.unsplash.com/400x400/?cocktail,party&v=1");

const changeImage = () => {
  imgSrc.value = `https://source.unsplash.com/400x400/?cocktail,party&v=${Math.floor(
    Math.random() * 300
  )}`;
};

const imgStyle = computed(() => {
  return {
    "border-width": "20px",
    borderStyle: "solid",
    borderColor: borderColor.value,
    filter: `grayscale(${grayscaleFilter.value}%)`,
  };
});

</script>
