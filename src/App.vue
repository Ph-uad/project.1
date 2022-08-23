<template>
  <header class="header">
    <Header msg="Vue Pizza Web-App " />
  </header>
  <div class="main">
    <Options msg="option1" @addToCart="addToCart" />
  </div>
  <Cart :data="cartData"/>
</template>

<script>
import Header from "./components/Header.vue";
import Options from "./components/Options.vue";
import Cart from "./components/Cart.vue";

export default {
  name: "App",
    components: {
    Header,
    Options,
    Cart
  },
  data(){
    return {
      cartData : [],
    }
  },
  methods: {
    addToCart (pizza){
      console.log(pizza)
      this.cartData.push(pizza)
    }
  }
};
</script>


<style>

</style>
