<template>
    <div id="cocktails">
        <button onclick="showDiv()" class="container">
            <img :src="data.drinks[0].strDrinkThumb" />
            <h2>{{ data.drinks[0].strDrink }}</h2>
        </button>

        <a href="#" class="container">
            <img :src="datatwo.drinks[0].strDrinkThumb" />
            <h2>{{ datatwo.drinks[0].strDrink }}</h2>
        </a>

        <a href="#" class="container">
            <img :src="datathree.drinks[0].strDrinkThumb" />
            <h2>{{ datathree.drinks[0].strDrink }}</h2>
        </a>
    </div>

    <div class="fullpage">
        <div class="cocktailheader">
            <img :src="data.drinks[0].strDrinkThumb+`/preview`" />
                <div class="details">
                    <h2>{{ data.drinks[0].strDrink }} <small>({{ data.drinks[0].strAlcoholic }})</small></h2>
                    <p>Drink category: {{ data.drinks[0].strCategory }}</p>
                    <p>Glass type: {{ data.drinks[0].strGlass }}</p>
                    <p>Ingredients:</p>
                    <p>{{ data.drinks[0].strIngredient1 }} {{ data.drinks[0].strMeasure1 }}</p>
                    <p>{{ data.drinks[0].strIngredient2 }} {{ data.drinks[0].strMeasure2 }}</p>
                    <p>{{ data.drinks[0].strIngredient3 }} {{ data.drinks[0].strMeasure3 }}</p>
                    <p>{{ data.drinks[0].strIngredient4 }} {{ data.drinks[0].strMeasure4 }}</p>
                    <p>{{ data.drinks[0].strIngredient5 }} {{ data.drinks[0].strMeasure5 }}</p>
                    <p>{{ data.drinks[0].strIngredient6 }} {{ data.drinks[0].strMeasure6 }}</p>
                </div>
        </div>
        <p id="instructions">{{ data.drinks[0].strInstructions }}</p>
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

<script>
    export default {
        methods: {
        showDiv () {
            document.getElementsByClassName('fullpage').element.style.setProperty('display', 'block');
        }
        }
    }
</script>

<style>

button:hover {
    opacity: 70%;
    cursor: pointer;
}
.container {
    display: flex;
    height: 310px;
    width: 300px;
    background-color: white;
    flex-direction: column;
    font-size: medium;
    border-radius: 15px;
    border: 4px solid #04383F;
    margin: 30px 30px;
    overflow: hidden;
    justify-content: center;
    align-items: center;
    position: relative;
    box-shadow: 2px 2px 8px 0px #000000;
    color: white;
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
    margin-bottom: 40px;
    position: relative;
}

#cocktails h2 {
    background-color: #04383F;
    color: white;
    width: 308px;
    overflow: hidden;
    position: absolute;
    bottom: -20px;
    border-bottom-left-radius: 8px;
    border-bottom-right-radius: 8px;
    padding: 5px 0px;
    border-top: 2px white solid;
}

.fullpage {
    height: 100%;
    max-width: 1050px;
    display: none;
    margin: auto;
    border-radius: 15px;
    border: 4px solid #04383F;
    z-index: 100;
    background-color: #04383F;
    box-shadow: 2px 2px 8px 0px #000000;
    margin-bottom: 50px;
    /* display: flex; */
    flex-direction: column;
    color: white;
    text-align: left;
}

.fullpage img {
    border-radius: 15px;
    height: 315px;
    width: 315px;
}

.cocktailheader {
    display: flex;
    flex-direction: row;
    padding: 0;
    margin: 0;
    color: white;
}

.details {
    display: flex;
    flex-direction: column;
    text-align: start;
    margin-left: 40px;
}

.details h2 {
    text-decoration: underline;
}

.details p {
    margin-top: -1px;
}

#instructions {
    padding: 25px;
}

@media screen and (max-width: 1200px) {
  .fullpage {
    width: 80%;
  }
}

@media screen and (max-width: 800px) {
  .cocktailheader {
    flex-direction: column;
    justify-content: center;
    align-items: center;
    display: flex;
  }

  .fullpage {
    display: flex;
    justify-content: center;
    align-items: center;
    max-width: 350px;
  }

  .details {
    display: flex;
    justify-content: center;
    margin: 0;
  }

  #instructions {
    margin: 0;
  }
}

</style>