<script>
import axios from 'axios';
import {store} from './store';

export default{
  name: 'app',
  components:{
    
  },
  data(){
    return{
      store
    }
  },
  created(){

  },
  methods: {
    callApi(){
      if(store.archtypeValue !== ''){
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=64e0fd76883f9c2095642a9cdab08e9e&language=it_IT&query=${store.movieValue}`)
           .then(res => {
             console.log(res.data)
             const datiApi = res.data
             this.store.arrayMovies = datiApi
           })
      } else{
        axios.get('https://api.themoviedb.org/3/search/movie?api_key=64e0fd76883f9c2095642a9cdab08e9e&language=it_IT&query=')
           .then(res => {
             console.log(res.data)
             const datiApi = res.data
             this.store.arrayMovies = datiApi
           })
      }
      // axios.get(`https://api.themoviedb.org/3/search/movie?api_key=64e0fd76883f9c2095642a9cdab08e9e&language=it_IT&query=${store.movieValue}
      // .then((res) =>{
      //   console.log(res.data)
      //   store.arrayMovies = res.data
      // })
    }
  }
}
</script>

<template>
  <div id="tutto">
    
  </div>
  
  
</template>

<style lang="scss">
@use './style/main.scss' as *;

#tutto{
height: 100vh;
}


</style>
