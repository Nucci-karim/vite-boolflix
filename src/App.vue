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
