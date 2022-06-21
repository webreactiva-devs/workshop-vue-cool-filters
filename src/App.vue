<template>
 <h1>{{appName}}</h1>
 <img :src="imgSrc" />
</template>

<script>
export default {
  data() {
    return {
      appName: 'Vue Cool Filters',
      imgSrc: 'https://source.unsplash.com/200x200/?cocktail,party&v=1'
    }
  }
} 
</script>