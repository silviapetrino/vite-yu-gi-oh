
<script>

import Header from './components/Header.vue';
import ContainerCards from './components/ContainerCards.vue';
import loader from './components/partials/loader.vue';
import SelectType from './components/partials/SelectType.vue';

import { store } from './data/store';
import axios from 'axios';

  export default {
    name: "AppVue",
    components: {
      Header,
      ContainerCards,
      loader,
      SelectType

    },
    data(){
      return{
        store

      }
    },
 
    
    methods: {
    getApi() {
      
      axios.get(store.apiUrl, {
        params: {
          archetype: "alien"
        }
      }) 
        .then((result) => {
          store.cardList = result.data.data;
          store.isLoading = false
        })
        .catch((error) => {
          error.data = "Pagina non trovata";
          store.isLoading = false
        })
    }
  },

    mounted(){
      this.getApi()
      
     
    }
  }
</script>


<template>

  <Header />
  <loader v-if="store.isLoading" />
  <SelectType />
  <ContainerCards />

</template>


<style lang="scss">

@use "./scss/main.scss" as *;

body {
  background-color: #CE8E2E;
}

</style>