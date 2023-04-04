<template>
  <div class="Cart">
    <h2 class="head">{{ name }}</h2>
    <img :src="image" :alt="name" />
    <h3>Price: ${{ price }}</h3>
    <h3>Quantity: {{ count }}</h3>
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
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  height: 20vh;
  width: 100%;
  margin: 1rem auto;
  align-items: center;
  background-color: var(--secondary);
  border: solid;
  border-radius: 1rem;
  border: 1px solid;
  color: var(--inv);
  box-shadow: var(--shadow) 0px 3px 8px;
}

.Cart > img {
  width: 5%;
  height: 25%;
  border-radius: 1rem;
};

button{
  text-align: center;
  margin: 1rem auto;
  font-size: 2rem;
  background-color: var(--yellow);
  transition: border-color 0.25s;
  border-radius: 8px;
  border: solid;
  padding: 0.6em 1.2em;
  font-size: 2em;
  font-weight: 700;
  font-family: inherit;
  cursor: pointer;
  color: var(--lightbrown);
  border-color: var(--inv);
}

button:hover {
  border-color: #646cff;
}
button:focus,
button:focus-visible {
  outline: 4px auto -webkit-focus-ring-color;}


body {background-color: var(--primary)};




</style>
