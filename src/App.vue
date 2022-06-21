<template>
  <img v-if="showImg" :src="imgSrc" />
  <div v-else>No te muestro la imagen y punto</div>
  <img v-for="image in images" :key="image" :src="image" />
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
};
</script>
