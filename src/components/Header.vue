
<script>
export default {
  name: "Header"
}
</script>



<template>
  <header class="d-flex p-2 align-items-center">
    <img src="../../public/Yugioh_anime_logo.webp" width="80">
    <h1>Yu-Gi-Oh Api</h1>
  </header>
</template>


<style lang="scss" scoped>
@use '../scss/partials/vars' as *;

header {
  background-color: $secondary-color;
  h1 {
    font-size: 2rem;
  }

}



</style>