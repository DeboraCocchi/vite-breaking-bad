<script>
import {store} from '../data/store'
export default {
  name:'AppHeader',
  props:{
    title:String
  },
  data(){
    return{
      store
    }
  }
}
</script>
<template>
  <header class="container-fluid">
    <div class="dc-container row">
      <a href="#" class="col-2">
        <img class="logo" src="../assets/bb-logo.png" alt="breaking-bad-logo">
      </a>
      <h2 class="col-8">{{title}}</h2>

      <div class="dropdown col-2">
        <select class="btn btn-success dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false" v-model="store.seriesToSearch" >
          <option class="dropdown-item" selected value="">Choose category</option>
          <option class="dropdown-item" value="Breaking Bad">Breaking Bad</option>
          <option class="dropdown-item" value="Better Call Saul">Better Call Saul</option>
        </select>
      </div>
    </div>
    
  </header>
</template>


<style lang="scss" scoped>
  
  @use '../styles/partials/variables' as *;
  
  header{
    height:66px;
    width:100%;
    background-color: white;
    &>.dc-container{
      height:100%;
      padding: 8px;
      align-items: center;
      justify-content: space-between;
      flex-wrap: nowrap;
      a{
        padding:0;
        img.logo{
        height:50px;
        }
      }
      h2{
      text-align: center;
      font-size:2rem;
      padding:0;
      margin:0;
      color:$primary-color;
      }
      .dropdown.col-2{
       text-align: right;
      }
  }
}
</style>