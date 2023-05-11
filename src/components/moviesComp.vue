<script>
import singleMovieComp from './singleMovieComp.vue';
import { store } from '../store';

export default{
  name: 'moviesComp',
  components:{
    singleMovieComp,
  },
  data(){
    return{
      store
    }
  },
}
</script>

<template>
  <div id="movies" class="container d-flex align-items-center">
      <singleMovieComp v-for="(movie, index) in store.arrayMovies"
    :key="index"
    :info="movie"/>
    
      <singleMovieComp v-for="(tv, index) in store.arrayTVseries"
    :key="index"
    :info="tv"/>
    
  </div>
</template>

<style lang="scss" scoped>
#movies{
    justify-content: center;
    flex-wrap: wrap;
}
</style>