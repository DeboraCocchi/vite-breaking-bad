<script>
export default {
  name:'AppHeader',
  props:{
    title:String
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
      <div class="input-group col-2 p-0">
        <button class="btn btn-outline-success dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="true">Select Category</button>
        <ul class="dropdown-menu">
          <li><a class="dropdown-item" href="#">Alive</a></li>
          <li><a class="dropdown-item" href="#">Dead</a></li>
        </ul>
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
      .input-group.col-2{
       text-align: right;
      }
  }
}
</style>