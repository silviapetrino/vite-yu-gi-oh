<script>

export default {
  name: "singol-card",

  props: {
    imgObj: Object,
    titleObj: String,
    typeObj: String
  }
}
</script>

<template>

    <div class="card-sp">
      <img :src="imageObj" :alt="titleObj">
      <h5> {{ titleObj }} </h5>
      <h6> {{ typeObj }} </h6>
    </div>


</template>



<style lang="scss" scoped>

.card-sp {
  background-color: #CE8E2E;
  border: 1px solid black;
  width: calc(100% / 5);
  h5 {
    color: white;
  }
  h6 {
    color: black;
  }
}

</style>