<script>

export default {
  name: "singol-card",

  props: {
    imgObj: String,
    titleObj: String,
    typeObj: String
  }
}
</script>

<template>

    <div class="card-sp">
      <img :src="imgObj">
      <h5> {{ titleObj }} </h5>
      <h6> {{ typeObj }} </h6>
    </div>


</template>



<style lang="scss" scoped>

.card-sp {
  margin: 10px 10px;
  background-color: #CE8E2E;
  width: calc(100% / 5 - 20px);
  text-align: center;
  display: flex;
  flex-direction: column;
  gap: 15px;


  h5, h6 {
    text-transform: uppercase;
  }
  h5 {
    color: white;
    font-size: 1rem;
    font-weight: 700;
  }
  h6 {
    color: black;
  }
}

</style>