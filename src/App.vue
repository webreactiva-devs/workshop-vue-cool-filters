<template>
  <button @click="changeImage">Cambiar imagen</button>
  <input type="color" v-model="borderColor" />
  <hr />
  <img :src="imgSrc" :style="imgStyle" />
</template>

<script setup>
import { ref, computed, onMounted } from "vue";

const borderColor = ref("#FF0000");
const imgSrc = ref("https://source.unsplash.com/200x200/?cocktail,party&v=1");

const changeImage = () => {
  imgSrc.value = `https://source.unsplash.com/200x200/?cocktail,party&v=${Math.floor(
    Math.random() * 300
  )}`;
};

const imgStyle = computed(() => {
  return {
    "border-width": "20px",
    borderStyle: "solid",
    borderColor: borderColor.value,
  };
});

onMounted(() => {
  document.querySelector('img').style.borderColor = 'blue'
})

</script>
