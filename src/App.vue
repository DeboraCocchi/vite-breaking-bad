<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import CharactersList from './components/CharactersList.vue'

export default {
  name:'App',
  components:{
    AppHeader,
    AppMain,
    CharactersList
  }
}
</script>

<template>
<AppHeader title="Breaking Bad Api"/>
<CharactersList/>
</template>


<style lang="scss">
 @use '/src/styles/general.scss';
</style>