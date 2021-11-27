<template>
  <div class="text-center mb-5 py-3">
      <img :src="disc.poster" :alt="disc.title">
      <h4 class="text-uppercase font-weight-bold my-2">{{disc.title}}</h4>
      <p class="m-0">{{disc.author}}</p>
      <p class="m-0">{{disc.year}}</p>
  </div>
  
</template>

<script>
export default {
   name: 'Disc',
   props:{
      disc: Object
   }
}
</script>

<style lang="scss" scoped>
@import '../assets/style/vars.scss';

div{
  width: 19%;
  margin: 0 0.5%;
  flex-shrink: 1;
  min-height: 400px;
  background-color: $second-color;
  img{
    width: 80%; 
  }
  h4 {
    color: $title-color;
  }
  p {
    color: $subtitle-color;
  }
}
</style>