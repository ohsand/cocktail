<template>
    <div id="cocktails">
        <div class="container">
            <img :src="data.drinks[0].strDrinkThumb" />
            <h2>{{ data.drinks[0].strDrink }}</h2>
        </div>

        <div class="container">
            <img :src="datatwo.drinks[0].strDrinkThumb" />
            <h2>{{ datatwo.drinks[0].strDrink }}</h2>
        </div>

        <div class="container">
            <img :src="datathree.drinks[0].strDrinkThumb" />
            <h2>{{ datathree.drinks[0].strDrink }}</h2>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
const data = ref(null);
const datatwo = ref(null);
const datathree = ref(null);
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
fetch('https://www.thecocktaildb.com/api/json/v1/1/random.php')
  .then((res) => res.json())
  .then((json) => (datathree.value = json))
  .catch((err) => (error.value = err));
  
</script>   

<style>
.container {
    display: flex;
    height: 310px;
    width: 300px;
    background-color: white;
    flex-direction: column;
    font-size: medium;
    border-radius: 15px;
    border: 4px solid #04383F;
    margin: 30px 50px;
    overflow: hidden;
    justify-content: center;
    align-items: center;
    position: relative;
    box-shadow: 2px 2px 8px 0px #000000;
}

.container img {
    object-fit: cover;
    scale: .45;
    width: max-content;
}

#cocktails {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    margin-top: 50px;
    position: relative;
}

#cocktails h2 {
    background-color: #04383F;
    color: white;
    width: 308px;
    /* position: relative;
    bottom: 260px;
    height: fit-content; */
    overflow: hidden;
    position: absolute;
    bottom: -20px;
    /* bottom: 430px; */
    border-bottom-left-radius: 8px;
    border-bottom-right-radius: 8px;
    padding: 5px 0px;
    border-top: 2px white solid;
}
</style>