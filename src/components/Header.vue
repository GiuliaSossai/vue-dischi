<template>
  <header>
     <div class="container-fluid">
        <div class="logo-img">
           <img src="../assets/img/logo.png" alt="">
        </div>
     </div>
  </header>
</template>

<script>
export default {
   name: 'Header'
}
</script>

<style lang="scss">
   @import '../assets/style/vars.scss';

   header {
      background-color: $second-color;
      padding: 1rem;
      margin-bottom: 3rem;
      img {
         width: 50px;
      }
   }

</style>