<template>
  <div class="loader text-center">
     <h5>{{textLoader}}</h5>
      <div class="lds-hourglass"></div>
  </div>
</template>

<script>

export default {
   name: 'Loading',
   props: {
      textLoader: String
   }
   
}
</script>

<style lang="scss" scoped>
   @import '../assets/style/vars.scss';

   .loader {
      padding-top: 20%;
      color: $title-color;
      .lds-hourglass {
      display: inline-block;
      position: relative;
      width: 80px;
      height: 80px;
      }
      .lds-hourglass:after {
      content: " ";
      display: block;
      border-radius: 50%;
      width: 0;
      height: 0;
      margin: 8px;
      box-sizing: border-box;
      border: 32px solid $subtitle-color;
      border-color: $subtitle-color transparent $subtitle-color transparent;
      animation: lds-hourglass 1.2s infinite;
      }
      @keyframes lds-hourglass {
      0% {
         transform: rotate(0);
         animation-timing-function: cubic-bezier(0.55, 0.055, 0.675, 0.19);
      }
      50% {
         transform: rotate(900deg);
         animation-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1);
      }
      100% {
         transform: rotate(1800deg);
      }
      }

   }
</style>