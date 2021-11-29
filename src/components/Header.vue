<template>
  <header @selectGenre="chooseGenre">
     <div class="container-fluid d-flex justify-content-between">
        <div class="logo-img">
           <img src="../assets/img/logo.png" alt="">
        </div>

        <Select />
     </div>
  </header>
</template>

<script>
import Select from './Select';

export default {
   name: 'Header',
   components: {
      Select
   },

   data(){
      return {
         selection: ''
      }
   },

   methods: {
      chooseGenre(selectedGenre){
         this.selection = selectedGenre;
         console.log('genere scelto in header', this.selection);
         this.$emit('fromHeader', this.selection);
      }
   }
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