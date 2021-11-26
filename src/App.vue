<template>
  <div class="main-wrapper">
    <Header />
    
    <div class="container">
      <MusicList />
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import MusicList from './components/MusicList.vue';

export default {
  name: 'App',
  components: {
    Header,
    MusicList
  }
}
</script>

<style lang="scss">

  @import './assets/style/vars.scss';
  @import './assets/style/generals.scss';

  .main-wrapper {
    min-height: 100vh;
  }
</style>
