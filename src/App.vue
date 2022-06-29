<template>
  <img :src="state.imgSrc" :style="imgStyle" />
  <hr />
  <button @click="changeImage">Cambiar imagen</button>
  <input type="color" v-model="state.borderColor" />
  <hr />
  <label for="grayscaleFilter">Escala de gris</label>
  <input
    type="range"
    v-model="state.grayscaleFilter"
    min="0"
    max="100"
    step="1"
  />
  <hr />
  <SaturateInputFilter
    v-model="state.saturateFilter"
    :min="0"
    :max="100"
    :step="1"
    label="Saturación"
    >Saturación<template #info
      ><small
        >Desliza el punto sobre la guía para cambiar la saturación de la
        imagen</small
      ></template
    ></SaturateInputFilter
  >
</template>

<script setup>
import { ref, computed, reactive } from "vue";
import SaturateInputFilter from "./components/SaturateInputFilter.vue";

const state = reactive({
  borderColor: "#FF0000",
  grayscaleFilter: 0,
  saturateFilter: 100,
  imgSrc: "https://source.unsplash.com/400x400/?cocktail,party&v=1",
});

const changeImage = () => {
  state.imgSrc = `https://source.unsplash.com/400x400/?cocktail,party&v=${Math.floor(
    Math.random() * 300
  )}`;
};

const changeSaturateFilter = (value) => {
  state.saturateFilter = value;
};

const imgStyle = computed(() => {
  return {
    "border-width": "20px",
    borderStyle: "solid",
    borderColor: state.borderColor,
    filter: `grayscale(${state.grayscaleFilter}%) saturate(${state.saturateFilter}%)`,
  };
});
</script>
