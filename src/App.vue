<script>
import axios from 'axios';
import {store} from './store';
import headerComp from './components/headerComp.vue'
import moviesComp from './components/moviesComp.vue'

export default{
  name: 'app',
  components:{
    headerComp,
    moviesComp,
  },
  data(){
    return{
      store
    }
  },
  // created(){
  //   this.ricercaApi()
  // },
  
}
</script>

<template>
  <div id="tutto">
    <header class="sticky-top">
      <headerComp/>
    </header>
    <main class="overflow-auto">
      <moviesComp/>
    </main>
  </div>
  
  
</template>

<style lang="scss">
@use './style/main.scss' as *;

#tutto{
height: 100vh;
}
main{
  height: 90%;
  background-color: rgb(59 59 59);
}
header{
  height: 10%;
  background-color: black;
}


</style>
