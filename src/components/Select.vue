<template>
  <select 
   class="form-control"
   v-model="genre"
   @change="selectValue"
  >
      <option value="tutti">Tutti i generi</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
   </select>
   
</template>

<script>
export default {
 name: 'Select',
 data(){
   return {
      genre: ''
   }
 },
 
 computed: {
   selectValue(){
      console.log('genere selezionato in select', this.genre);
      return this.$emit("selectGenre", this.genre);
   }
 }
}
</script>

<style lang="scss" scoped>
   .form-control {
      width: 200px;
   }
</style>