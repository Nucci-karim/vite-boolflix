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
    'dettagli',
  ],
  components: {
    
  },
  
}
</script>

<template>
  <div id="card" class="card col-3">
    <img src="..." :alt="dettagli.original_title">
    <div class="card-body">
        <h4 class="card-title">{{dettagli.title}}</h4>
        <span class="card-text">{{dettagli.original_title}}</span>
    </div>
    
  </div>
</template>

<style lang="scss" scoped>
#card{
    margin: 0.5rem;
}

</style>