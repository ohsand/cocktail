<template>
  <WebpageHeader />
  <ShakerText />
  <MainpageCocktail />
  
</template>

<script>
import WebpageHeader from './components/header'
import MainpageCocktail from './components/cocktail'
import ShakerText from './components/shakertext'


export default {
  name: 'App',
  components: {
    WebpageHeader,
    MainpageCocktail,
    ShakerText
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #04383F;
  padding: 0;
  margin: 0;
}

</style>
