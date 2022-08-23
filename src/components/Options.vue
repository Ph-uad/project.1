<template>
  <ul>
    <li v-for="pizza in pizzas" :key="pizza.name" class="option">
      <img src="../assets/food.jpg" alt="piz option" srcset=""  class="img option__img"/>
      <div class="flex">
        <h3 class="heading__tertiary">{{ pizza.name }}</h3>
        <p>{{ pizza.size }}</p>
      </div>

      <form class="flex">
        <input
          class="form__input"
          type="number"
          name=""
          id=""
          v-model="pizza.amount"
          min="1"
        />
        <button class="btn form__btn" @click="submitForm($event, pizza)" name="">Add</button>
      </form>
    </li>
  </ul>
</template>

    
<script>
export default {
  data() {
    return {
      pizzas: [
        { name: "Pepperoni type Hot", size: "Large", price: 2300, amount: 0 },
        { name: "Pepperoni type Hot1", size: "Large", price: 2100, amount: 0 },
        { name: "Pepperoni type Hot2", size: "Large", price: 1200, amount: 0 },
        { name: "Pepperoni type Hot3", size: "Large", price: 2500, amount: 0 },
      ],
      cartItems: [],
    };
  },
  methods: {
    submitForm(e, pizza) {
      e.preventDefault();
      if (pizza.amount > 0) {
        const cartBtn = document.querySelector(".cart__btn");
        cartBtn.classList.add("animate");
        pizza.totalAmount = pizza.amount * pizza.price;
        this.$emit("addToCart", pizza);
        setTimeout(() => {
          cartBtn.classList.remove("animate");
        }, 200);
      }
    },
  },
};
</script>


