<script>
export default {
  name:'CharacterCard',
  props:{
    char:Object
  }
}
</script>
<template>
  <div class="card dc-card col-2">
    <img :src="char.img" class="card-img-top" :alt="char.name">
    <div class="card-body">
      <h5 class="card-title">{{char.name}}</h5>
      <h6 class="card-title nickname">{{char.nickname}}</h6>
      <p class="card-text status">{{char.status}}</p>
      <a href="#" class="btn btn-warning">Scopri di più</a>
    </div>
</div>
</template>


<style lang="scss" scoped>

@use '../styles/partials/variables.scss' as *;

  .dc-card{
    margin:8px;
    background-color: $primary-color;
    border-radius:10px;
    color:white;
    padding:0;
  }
  .dc-card>img{
    height:75%;
    width:100%;
    object-fit:cover;
    background-color: rgba(255,255,255,0.5);
    border-top-right-radius: 10px;
    border-top-left-radius: 10px;
  }
  .dc-card>.card-body{
    text-align:center;
    padding:8px 3px;
    border-bottom-right-radius: 10px;
    border-bottom-left-radius: 10px;
    background-color: $primary-color;
      &>*{
      margin-bottom:2px;
      }
    .nickname{
      text-transform: uppercase;
      font-weight:bold;
      position: relative;
      top: 0px;
      font-size: 140%;
      color: #ffc107;
      line-height: 1.1rem;
    }
    .status{
      font-size:70%;
      font-weight:300;
    }
    a.btn-warning{
      width:80%;
      font-size: 80%;
      padding:5px 8px;
    }
  }
</style>