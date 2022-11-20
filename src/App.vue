<script>
import axios from 'axios'
import {store} from '../src/data/store'
import AppHeader from '../src/components/AppHeader.vue'
import CharactersList from '../src/components/CharactersList.vue'
import CharacterCard from '../src/components/CharacterCard.vue'


export default {
  name:'App',
  components:{
    AppHeader,
    CharactersList,
    CharacterCard
  },
  data(){
    return{
      store
    }
  },
  methods:{
    getApiCall(){
      store.isLoaded = false;
      store.charsList=[];
      console.log(axios.get(store.apiUrl))
      axios.get(store.apiUrl, {
        params:{
          category:store.seriesToSearch
        }
      })
      .then( result =>{
         store.charsList = result.data;
         store.isLoaded = true;
      })
      .catch( error =>{
        console.log(error);
      })
    }
  },
  created(){
    this.getApiCall();
    console.log('lanciata!');
  }

}
</script>

<template>
<AppHeader title="Breaking Bad Api" @cambiaSerie="getApiCall"/>

<CharactersList/>


</template>


<style lang="scss">
 @use '/src/styles/general.scss';

 
</style>