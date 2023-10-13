
<script>
import axios from 'axios';
import { store } from '../../data/store';
export default {
  name: "select-type-bar",
  data(){
    return{
      store
    }
  },

  methods: {
    getApi() {
      axios.get(store.apiUrlType)
      .then((res) => {
        store.listOftypes = res.data
        // console.log(store.listOftypes)
      })
    },

    changeType() {
      console.log(this.store.selectedType)
      axios.get(store.apiUrlType)
      .then((res) => {
        store.listOftypes = res.data
      })
      .catch((err) => {
        console.log(err + "errore")
      })
    }
    
  },

  mounted(){
    this.getApi()
  }
}
</script>


<template>

<select @change="changeType" v-model="store.selectedType" class="form-select form-select-sm" aria-label="Small select example">
  <option @click="$emit('searchTypeGo')" v-for="(type, index) in store.listOftypes" :key="`type${index}`" :value="type.archetype_name">{{ type.archetype_name }}</option>
</select>
  

</template>



<style lang="scss" scoped>

select {
  width: 200px;
  margin: 30px 60px 0px 100px;
}

</style>