<template>
  <button @click="toggleShowImg">Interruptor</button>
  <button @click="changeImage">Cambiar imagen</button>
  <hr />
  <img v-if="showImg" :src="imgSrc" />
  <div v-else>No te muestro la imagen y punto</div>
</template>

<script>
export default {
  data() {
    return {
      showImg: true,
      imgSrc: "https://source.unsplash.com/200x200/?cocktail,party&v=1",
      images: [
        "https://source.unsplash.com/200x200/?cocktail,party&v=2",
        "https://source.unsplash.com/200x200/?cocktail,party&v=3",
        "https://source.unsplash.com/200x200/?cocktail,party&v=4",
        "https://source.unsplash.com/200x200/?cocktail,party&v=5",
      ],
    };
  },
  methods: {
    toggleShowImg() {
      return this.showImg = !this.showImg
    },
    changeImage() {
      //return this.imgSrc = this.images[Math.floor(Math.random() * this.images.length)];
      return this.imgSrc = `https://source.unsplash.com/200x200/?cocktail,party&v=${Math.floor(Math.random() * 300)}`;
    }
  }
};
</script>
