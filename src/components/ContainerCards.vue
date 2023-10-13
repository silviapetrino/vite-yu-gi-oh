<script>
import axios from 'axios';
import singolCard from './partials/singolCard.vue';
import { store } from '../data/store';
import SelectType from './partials/SelectType.vue';


export default {
  name: "card-container",
  components: {
    singolCard,
    SelectType,
    

  },
  data(){
    return {
      store
    }
  },
  methods: {
    filterTypeSelected() {
      let url = this.store.apiUrl + "?archetype=" + this.store.selectedType;

      if(this.store.selectedType === null) {
        this.url = this.store.apiUrl 
      } else {
        this.url = this.store.apiUrl + "?archetype=" + this.store.selectedType;
      }
      console.log(this.url)
      
    }
  },

  mounted(){
    this.filterTypeSelected()
  }
 
 
}
</script>


<template>
<SelectType @type-selected="filterTypeSelected" />
  <div class="container">
    
    <div class="row">

      <singolCard v-for="singolCard in store.cardList" :key="singolCard.id"
      :imgObj="singolCard.card_images[0].image_url_small"
      :titleObj="singolCard.name"
      :typeObj="singolCard.archetype"
      
      />
  
    </div>
    
  </div>
  
</template>



<style lang="scss" scoped>


.container {
  margin: 60px auto;
  width: 80%;
  background-color: rgb(255, 255, 255);
  .row {
    justify-content: space-between;
    flex-direction: flex-start;
  }
}

</style>