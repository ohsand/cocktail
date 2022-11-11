<template>
    <div id="cocktails">
    <div class="container">
       <h1>{{ data.drinks[0].strDrink }}</h1>
       <!-- <button @click={console.log(cocktail)}>Show a cocktail</button> -->
    </div>

    <div class="container">
       <h1>{{ datatwo.drinks[0].strDrink }}</h1>
       <!-- <button @click={console.log(cocktail)}>Show a cocktail</button> -->
    </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
const data = ref(null);
const datatwo = ref(null);
const error = ref(null);
fetch('https://www.thecocktaildb.com/api/json/v1/1/random.php')
  .then((res) => res.json())
  .then((json) => (data.value = json))
  .catch((err) => (error.value = err));
  console.log(data)
fetch('https://www.thecocktaildb.com/api/json/v1/1/random.php')
  .then((res) => res.json())
  .then((json) => (datatwo.value = json))
  .catch((err) => (error.value = err));
</script>

<style scoped>
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 300px;
    width: 300px;
    background-color: green;
    flex-direction: column;
    font-size: medium;
    border-radius: 15px;
    border: 2px solid black;
    margin: 15px;
}

#cocktails {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    
}
</style>