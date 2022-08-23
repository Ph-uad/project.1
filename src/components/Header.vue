<template>
  <header class="header">
    <h1 class="heading__primary">{{ msg }}</h1>
    <img class="header__img" alt="Pizza" src="../assets/hero.jpg" />
  </header>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
