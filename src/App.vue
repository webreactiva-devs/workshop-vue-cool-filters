<template>
  <button @click="changeImage">Cambiar imagen</button>
  <input type="color" v-model="borderColor" />
  <hr />
  <img :src="imgSrc" :style="`border: 20px solid ${borderColor}`" />
</template>

<script>
export default {
  data() {
    return {
      borderColor: "#FF0000",
      imgSrc: "https://source.unsplash.com/200x200/?cocktail,party&v=1",
    };
  },
  methods: {
    changeImage() {
      return (this.imgSrc = `https://source.unsplash.com/200x200/?cocktail,party&v=${Math.floor(
        Math.random() * 300
      )}`);
    }
  },
};
</script>
