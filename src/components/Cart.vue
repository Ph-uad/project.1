<template >
  <teleport to=".cart">
    <div class="cart-modal">
      <button @click="showCartHandler" class="cart__btn btn">Cart Icon</button>
      <div @click.self="showCartHandler" v-if="doShowCart" class="modal">
        <div class="modal-content">
          <h4 class="heading heading--center">Cart Title</h4>
          <ul>
            <li v-for="item in data" :key="item.price" class="flex">
                <strong>{{item.name}}</strong>
                <p>{{item.size}}</p>
                <p>{{item.price}} x {{item.amount}}</p>
                <p>{{item.totalAmount}}</p>
            </li>
          </ul>
          
        </div>
      </div>
    </div>
  </teleport>
</template>

<script>
export default {
  props: ["data"],
  data() {
    return {
      doShowCart: false,
    };
  },
  methods: {
    showCartHandler() {
      this.doShowCart = !this.doShowCart;
      console.log(this.data)
    },
  },
};
</script>
    
<style>
.modal {
  position: fixed;
  top: 0%;
  left: 0%;
  background: rgba(0, 0, 0, 0.8);
  height: 100vh;
  width: 100vw;
  z-index: 10;
}

.modal-content {
  background: #eee;
  width: 50%;
  min-height: 30%;
  position: relative;
  top: 25%;
  border-radius: 1rem;
  padding: 1.5rem;
  margin: 0 auto;
}

.heading {
  text-transform: capitalize;
}

.heading--center {
  text-align: center;
}
</style>