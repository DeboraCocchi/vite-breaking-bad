<script>
export default {
  name:'AppHeader',
  props:{
    title:String
  }
}
</script>
<template>
  <header>
    <a href="#">
      <img src="../assets/bb-logo.png" alt="breaking-bad-logo">
    </a>
    <h2>{{title}}</h2>
  </header>
</template>


<style lang="scss" scoped>
@use '../styles/partials/variables' as *;
header{
  height:60px;
  width:100%;
  background-color: white;
  padding: 8px;
  a>img{
    max-height:100%;
  }
  h2{
    margin:0 auto;
    width:calc(100% - 75px);
    text-align: center;
    display:inline-block;
    font-size:150%;
    color:$primary-color;
  }
  
}
</style>