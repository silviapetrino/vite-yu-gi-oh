
<script>

import Header from './components/Header.vue';
import ContainerCards from './components/ContainerCards.vue';
import { store } from './data/store';
import axios from 'axios';

  export default {
    name: "AppVue",
    components: {
      Header,
      ContainerCards
    },
    data(){
      return{
        store,
        offset: Math.floor(Math.random() * 1000) + 1,
      
      }
    },
    methods: {
    getApi() {
      
      const apiUrlWithOffset = `https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=${this.offset}`;

      axios.get(apiUrlWithOffset)
        .then((result) => {
          store.cardList = result.data;
        })
        .catch((error) => {
          console.error('Errore');
        });
    }
  },

    mounted(){
      this.getApi()
      console.log(this.offset)
    }
  }
</script>


<template>
  
  <Header />
  <ContainerCards />

</template>


<style lang="scss">

@use "./scss/main.scss" as *;

body {
  background-color: #CE8E2E;
}

</style>