<script>
import {store} from '../data/store'
import CharacterCard from './CharacterCard.vue'
export default {
  name:'CharactersList',
  components:{
    CharacterCard
  },
  data(){
    return{
      store
    }
  }
}
</script>
<template>
  <div class="container dc-container">
      <div class="row" v-if="store.isLoaded">
        breaking bad
      </div>
      <div class="spinner" v-else>
        <img class="loader" src="../assets/mini_loader.png" alt="loading..."></div>
    </div>
</template>


<style lang="scss" scoped>
  .dc-container{
    width:70%;
    background-color:rgba(255,255,255,0.5);
    border-radius:10px;
    margin:20px auto;
  }

  .loader{
    height:80px;
    animation: heisenberg 1s ease-out infinite;
  }

  @keyframes heisenberg{
    0% {transform: rotate(0deg)}
    100% {transform: rotate(360deg)}
  }
</style>