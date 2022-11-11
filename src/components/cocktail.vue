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
    border: 3px solid #04383F;
    margin: 15px 30px;
    overflow: hidden;
    justify-content: center;
    align-items: center;
}

.container img {
    /* margin-top: 65px; */
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
}

#cocktails h2 {
    background-color: #04383F;
    color: white;
    width: 300px;
    /* position: relative;
    bottom: 260px;
    height: fit-content; */
    overflow: hidden;
    position: absolute;
    bottom: 430px;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    padding: 10px 0px;
    border-top: 2px white solid;
}
</style>