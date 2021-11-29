<template>
  <select 
   class="form-control"
   v-model="genre"
   @change="selectValue"
  >
      <option value="Tutti">Tutti</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
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
 
 methods: {
   selectValue(){
      console.log('genere in select', this.genre);
      this.$emit("selectGenre", this.genre);
      //oppure potevo mettere nel tag select:
      //@change="$emit('selectGenre', genre)"
   }
 }
}
</script>

<style lang="scss" scoped>
   .form-control {
      width: 200px;
   }
</style>