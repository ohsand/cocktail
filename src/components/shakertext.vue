<template>
    <h2>
       Click the shaker to discover new cocktails!
    </h2>
</template>

<script>
export default {
  name: 'ShakerText',
}
</script>

<style scoped>
h2 {
    display: flex;
    justify-content: center;
    align-items: center;
    color: #04383F;
    margin-top: 30px;
}

@media screen and (min-width: 800px) {
  h2 {
    margin-bottom: -30px;
  }
}

</style>