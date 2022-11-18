<script>
import {store} from '../data/store'
import CharacterCard from '../components/CharacterCard.vue'
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
<main>
  <div class="dc-container">
    <div class="container-fluid">
      <div class="row">
            <CharacterCard v-for="char in store.charsList"
            :key="char.id" :char="char"/>
      </div>
      <div class="spinner" v-show="!store.isLoaded">
        <img class="loader d-flex mt-4 m-auto" src="../assets/mini_loader.png" alt="loading..."></div>
    </div>

    </div>
</main>    
</template>


<style lang="scss" scoped>
  main{
    height:calc(100vh - 66px);
    overflow-y: scroll;
  }
  .dc-container{
    width:80%;
    border-radius:10px;
    margin:20px auto;
    overflow-y:auto;
    .row{
      display:flex;
      flex-wrap: wrap;
      justify-content: space-around;
      row>*{
        margin:0;
        padding:0;
      }
    }
  }

  .loader{
    height:80px;
    animation: heisenberg 0.5s ease-out infinite;
  }

  @keyframes heisenberg{
    0% {transform: rotate(0deg)}
    100% {transform: rotate(360deg)}
  }
</style>