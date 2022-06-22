<template>
  <button @click="changeImage">Cambiar imagen</button>
  <input type="color" v-model="borderColor" />
  <hr />
  <img :src="imgSrc" :style="imgStyle" />
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
  computed: {
    imgStyle() {
      return {
        "border-width": "20px",
        borderStyle: "solid", 
        borderColor: this.borderColor
      }
    },
  }
};
</script>
