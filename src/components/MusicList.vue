<template>
   <div>
      <div v-if="loaded"  class="row">
         <Disc 
            v-for="(disc, index) in filteredMusic"
            :key="index"
            :disc="disc"
         />  
      </div>

      <Loading v-else textLoader="Loading Music..."/>   
   </div>
  
</template>

<script>
import axios from 'axios';
import Disc from './Disc.vue';
import Loading from './Loading.vue';

export default {
   name: 'MusicList',
   props:{
      typeGenre: String
   },
   components: {
      Disc,
      Loading   
   },

   data(){
      return{
         discs: [],
         loaded: false,
         apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music'
      }
   },

   computed:{
      filteredMusic(){
         if(this.typeGenre == "" || this.typeGenre == "Tutti"){
          return this.discs;
         } else {
            let discsFiltered = this.discs.filter( album => {
               return album.genre.toUpperCase().includes(this.typeGenre.toUpperCase());
            });

            console.log('array filtrato', discsFiltered);
            return discsFiltered;
         }
           
      }
   },

   methods:{
      getApi(){
         //this.loaded = true;

         axios.get(this.apiUrl)
         .then((response) => {
            this.discs = response.data.response;
           
            this.loaded = true;
         })
         .catch((error) => {
            console.log(error);
         })
      }
   },

   mounted(){
      console.log(axios);
      this.getApi();
   }
}
</script>

<style>
</style>