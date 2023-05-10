<script>
import { store } from '../store';
import inputRicerca from './inputRicerca.vue';
import axios from 'axios';
export default{
  name: 'HeaderComp',
  components:{
    inputRicerca,
  },

  data(){
    return{
      store,
    }
  },
  created(){
    this.ricercaApi()
  },
  methods: {
    ricercaApi(){
      if(store.movieValue !== ''){
        axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${store.key}&query=${store.movieValue}`)
           .then(res => {
             console.log(res.data.results)
             const datiApiM = res.data.results
             this.store.arrayMovies = datiApiM

              axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${store.key}&query=${store.movieValue}`)
              .then(res => {
                console.log(res.data.results)
                const datiApiSTV = res.data.results
                this.store.arrayTVseries = datiApiSTV
            })
           })
           
      } else{
         axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${store.key}&query=batman`)
            .then(res => {
              console.log(res.data.results)
              const datiApi = res.data.results
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
  <div id="header" >
    <div class="container d-flex align-items-center justify-content-between">
      <h1 class="mx-2">BoolFlix</h1>
      <div>
        <inputRicerca @callApi="ricercaApi()"/>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
#header{
  background-color: rgb(0 0 0);
  h1{
  color: red;
  }
}

</style>