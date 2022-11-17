<script>
import AppHeader from './src/components/AppHeader.vue'
import AppMain from './src/components/AppMain.vue'
import CharactersList from './src/components/CharactersList.vue'

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