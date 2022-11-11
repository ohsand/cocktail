<template>
  <WebpageHeader />
  <MainpageCocktail />
  
</template>

<script>
import WebpageHeader from './components/header'
import MainpageCocktail from './components/cocktail'

export default {
  name: 'App',
  components: {
    WebpageHeader,
    MainpageCocktail
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
