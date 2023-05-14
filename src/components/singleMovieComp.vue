<script>
import { store } from '../store';

export default{
  name: 'singleMovieComp',
  data(){
    return{
      store
    }
  },
  props:[
    'info',

  ],

  components: {
    
  },
  methods :{
    // stampaBandiera(){
    //     if(this.info.original_language == 'en'){
    //         return ''
    //     } else if(this.info.original_language == 'it'){
    //         return ''
    //     } else{
    //         return '/'
    //     }
        
    // },
    apiBandiere(x){
        //https://flagsapi.com/${}/shiny/64.png
         x = x.toUpperCase();

         if(x == 'EN'){
            x = 'GB'
            return `https://flagsapi.com/${x}/shiny/64.png`
         }else {
            return `https://flagsapi.com/${x}/shiny/64.png`
         }

        
    },
    getTitle(){
        if(this.info.title){
            return this.info.title
        }else{
            return this.info.name
        }
    },
    getOriginalTitle(){
        if(this.info.original_title){
            return this.info.original_title
        }else{
            return this.info.original_name
        }
    },
    getVote(){
        return Math.ceil(this.info.vote_average / 2)
    },
  },
  
}
</script>

<template>
<div class="card col-3 margine">
    <img :src="'https://image.tmdb.org/t/p/w342'+ info.poster_path" :alt="getOriginalTitle()">
    <div class="card-body">
        <div class="d-flex align-items-center justify-content-between card-text">
            <h4 class="card-title">{{getTitle()}}</h4>
            <div class="d-flex align-items-center">
                <div class="card-text mx-2">{{ info.original_language }}</div>
                <img :src="apiBandiere(info.original_language)" alt="">
            </div>
        </div>
        <span class="card-text">Titolo Originale: {{getOriginalTitle()}}</span>
        <div class="d-flex align-items-center card-text">
            <div class="mx-2">voto: {{ getVote() }}</div>
            <span>
                <i v-for="n in 5" class="fa-star" :class="(n <= getVote()) ? 'fa-solid' : 'fa-regular'"></i>
            </span>
        </div>
    </div>
</div>
</template>

<style lang="scss" scoped>
.margine{
    margin: 0.5rem;
}

</style>