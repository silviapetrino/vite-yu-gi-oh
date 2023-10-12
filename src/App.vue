
<script>
import Header from './components/Header.vue';
import ContainerCards from './components/ContainerCards.vue';

  export default {
    name: "AppVue",
    components: {
      Header,
      ContainerCards
    }
  
  }
</script>


<template>
  
  <Header />
  <ContainerCards />

</template>


<style lang="scss">

@use "./scss/main.scss" as *;


</style>