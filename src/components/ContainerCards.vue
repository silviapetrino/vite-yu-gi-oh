<script>
import singolCard from './partials/singolCard.vue';
import { store } from '../data/store';


export default {
  name: "card-container",
  components: {
    singolCard

  },
  data(){
    return {
      store
    }
  }
 
 
}
</script>


<template>

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