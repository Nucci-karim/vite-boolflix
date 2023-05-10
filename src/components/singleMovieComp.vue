<script>
import { store } from '../store';

export default{
  name: 'singleMovieComp',
  data(){
    return{
      store
    }
  },
  props: [
    'dettagliM',
    'dettagliTV'
  ],
  components: {
    
  },
  
}
</script>

<template>
<div  class="card col-3 margine"
    v-for="(elem, index) in store.arrayMovies"
    :key="index">
    <img :src="'https://image.tmdb.org/t/p/w500'+ elem.poster_path" :alt="elem.original_title">
    <div class="card-body">
        <h4 class="card-title">{{elem.title}}</h4>
        <span class="card-text">{{elem.original_title}}</span>
    </div>
</div>
<div class="card col-3 margine" 
    v-for="(elem, index) in store.arrayTVseries"
    :key="index">
    <img :src="'https://image.tmdb.org/t/p/w500'+ elem.poster_path" :alt="elem.original_name">
    <div class="card-body">
        <h4 class="card-title">{{ elem.name }}</h4>
        <span class="card-text">{{ elem.original_name }}</span>
    </div>
</div>
</template>

<style lang="scss" scoped>
.margine{
    margin: 0.5rem;
}

</style>