<template>
  <button @click="changeImage">Cambiar imagen</button>
  <input type="color" v-model="borderColor" />
  <hr />
  <img :src="imgSrcComputed" :style="imgStyle" />
</template>

<script>
const getRandomNumber = () => Math.floor(Math.random() * 300)

export default {
  data() {
    return {
      borderColor: "#FF0000",
      randomNumber: getRandomNumber(),
      imgSrc: "https://source.unsplash.com/200x200/?cocktail,party&v=1",
    };
  },
  methods: {
    changeImage() {
      this.randomNumber = getRandomNumber()
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
    imgSrcComputed() {
      return `https://source.unsplash.com/200x200/?cocktail,party&v=${this.randomNumber}`
    }
  }
};
</script>
