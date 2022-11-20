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
  },computed:{
    outputSearch(){
      store.isLoaded=false;
      if(store.charsList.length>0){
        store.isLoaded=true;
        return `Trovati ${store.charsList.length} risultati`
      }
      return `Nessun risultato trovato`
    }
  }
}
</script>
<template>
<main>
  <div class="dc-container">
    <div class="results"><h4 v-show="store.isLoaded">{{outputSearch}}</h4>
      </div>
    <div class="container-fluid">
      <div class="row">
            <CharacterCard v-for="char in store.charsList"
            :key="char.id" :char="char"/>
      </div>
      <div class="spinner" v-show="!store.isLoaded">
        <img class="loader d-flex m-auto" src="../assets/mini_loader.png" alt="loading..."></div>
    </div>

    </div>
</main>    
</template>


<style lang="scss" scoped>

@use '../styles/partials/variables' as *;

  main{
    height:calc(100vh - 66px);
    overflow-y: scroll;
  }
  .dc-container{
    width:80%;
    border-radius:10px;
    margin:0 auto 20px;
    .results{
      color:white;
      h4{
        text-align:center;
        margin: 0 auto 20px;
        width:25%;
        background-color: $primary-color;
        font-size:95%;
        padding:10px 30px;
        border-bottom-left-radius: 15px;;
        border-bottom-right-radius: 15px;;
      }
    }
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
  .spinner{
    margin-top:100px;
    .loader{
    height:100px;
    animation: heisenberg 0.5s ease-out infinite;
  }
  }

  @keyframes heisenberg{
    0% {transform: rotate(0deg)}
    100% {transform: rotate(360deg)}
  }
</style>