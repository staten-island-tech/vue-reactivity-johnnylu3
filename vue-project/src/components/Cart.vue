<template>
  <div class="Cart">
    <h2>{{ name }}</h2>
    <img :src="image" :alt="name" />
    <p>${{ price }}</p>
    <p>Quantity: {{ count }}</p>
    <button @click="removeFromCart">Remove from cart</button>
  </div>
</template>

<script>
import { store } from '../components/store';
export default {
  name: 'Cart',
  props: {
    name: String, 
    price: Number,
    image: String,
    count: Number,
    index: Number,
  },
  data() {
    return {
    }
  },
  methods: {
    removeFromCart() {
      if (store.cart[this.index].count === 1) {
        store.cart.splice(this.index, 1);
      } else {
        store.cart[this.index].count--;
      }
    },
  },
}
</script>

<style>

.Cart {
  height: fit-content;
  display: flex;
  flex-direction:column ;
  padding: 1rem 1rem 2rem;
  background: #fff1ff;
  box-shadow: 0 0 40px rgba(0, 0, 0, 0.2), 0 0 40px rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  margin-bottom: 30px;
  color: black;
}
.Cart > img {
  width: 100%;
  height: auto;
}

</style>
