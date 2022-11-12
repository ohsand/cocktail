<template>
    <header>
       <!-- <h1>Cocktail Finder</h1> -->
       <img src="../assets/logowhite.png" alt="cocktail finder logo white" class="logo"/>
       <img src="../assets/shaker.png" alt="cocktail shaker" id="shaker" @click="randomize()"/>
    </header>
</template>

<script>
export default {
    name: 'WebpageHeader',
    methods: {
            randomize() {
                window.location.reload();
                }
            }
        }
</script>

<style scoped>
header {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 150px;
    background-color: #04383F;
    color: white;
}

#shaker {
    height: 100px;

}
#shaker:hover {
    cursor: pointer;
  animation: shake 0.82s cubic-bezier(.36,.07,.19,.97) both;
  transform: translate3d(0, 0, 0);
  backface-visibility: hidden;
  perspective: 1000px;
}

@keyframes shake {
  10%, 90% {
    transform: translate3d(-1px, 0, 0);
  }
  
  20%, 80% {
    transform: translate3d(2px, 0, 0);
  }

  30%, 50%, 70% {
    transform: translate3d(-4px, 0, 0);
  }

  40%, 60% {
    transform: translate3d(4px, 0, 0);
  } 
}
</style>