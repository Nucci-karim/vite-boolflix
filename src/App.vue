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
    <headerComp/>
    <main>
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
  background-color: rgb(59 59 59);
}


</style>
