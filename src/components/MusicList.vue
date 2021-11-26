<template>
   <div>
      <div v-if="loaded" class="row">
         <!-- v-for="(item, index) in discs"
            :key="index"
            :disc="disc" -->
         <Disc 
            v-for="(item, index) in discs"
            :key="index"
            
         />
         
      </div>
      <Loading textLoader="Loading Music..." v-else />
   </div>
  
</template>

<script>
import axios from 'axios';
import Disc from './Disc.vue';
import Loading from './Loading.vue';

export default {
   name: 'MusicList',
   components: {
      Disc,
      Loading
   },
   data(){
      return{
         discs: [],
         loaded: false,
         apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
         //index: ''
      }
   },
   methods:{
      getApi(){
         axios.get(this.apiUrl)
         .then((response) => {
            console.log('response', response);
            console.log('data', response.data);
   
            this.discs = response.data.response;
            console.log('discs array', this.discs);
            console.log('oggetto disc', this.discs[0]);
            
            console.log('autore oggetto 0:', this.discs[0].author);
            //console.log('img oggetto 3:', this.discs[this.index].poster);
            
           
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

<style lang="scss">
   .row {
      display: flex;
      flex-wrap: wrap;
   }
</style>