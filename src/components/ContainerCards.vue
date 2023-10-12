<script>
import singolCard from './partials/singolCard.vue';
export default {
  name: "card-container",
  components: {
    singolCard
  }
}
</script>


<template>

  <div class="container">
    <div class="row">

      <singolCard />
  
    </div>
    
  </div>
  
</template>



<style lang="scss" scoped>


.container {
  margin: 100px auto;
  width: 80%;
  background-color: rgb(255, 255, 255);
  .row {
    justify-content: space-between;
    flex-direction: flex-start;
  }
}

</style>