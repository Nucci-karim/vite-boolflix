<script>
import { store } from '../store';
export default{
  name: 'inputRicerca',

  data(){
    return{
      store
    }
  },
  
  
}
</script>

<template>
    <div>
        <input type="text" placeholder="Search Your Movie" v-model="store.movieValue">
        <button @click="$emit('callApi')">Search</button>
    </div>
</template>

<style lang="scss" scoped>

</style>