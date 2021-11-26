<template>
  <div class="text-center mb-5 py-3">
      <!-- <img :src="discs[index].poster" :alt="discs[index].title">
      <h4 class="text-uppercase font-weight-bold my-2">{{discs[index].title}}</h4>
      <p class="m-0">{{discs[index].author}}</p>
      <p class="m-0">{{discs[index].year}}</p> -->

      <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
      <h4 class="text-uppercase font-weight-bold my-2">new jersey</h4>
      <p class="m-0">bon jovi</p>
      <p class="m-0">1989</p>
  </div>
  
</template>

<script>
export default {
   name: 'Disc',
   props:{
      //discs: Array
      //disc: Object
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