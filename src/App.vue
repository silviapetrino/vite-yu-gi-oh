
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
        apiUrlWithOffset : `https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=${this.offset}`
      }
    },
    methods: {

      getApi(){
        axios.get(store.apiUrl)
        store.apiUrl = this.apiUrlWithOffset
        .then((result) => {
          store.cardList = result.data
        })
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