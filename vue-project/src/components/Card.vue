<template>
      <div class="card">
        <h2>{{ name }}</h2>
        <img :src="image" :alt="name" />
        <h3>{{ type }}</h3>
        <h3>Price: ${{ price }}</h3>
        <button @click="addToCart">Add to Cart</button>
      </div>
</template>

<script>
import { store } from '../components/store';
  export default {
    name: 'Card',
  props: {
    name: String, 
    type: String,
    price: Number,
    image: String,
  },

  methods: {
    addToCart() {
  let card = store.cart.find((item) => item.name === this.name);
  if (card) {
    card.count++;
    console.log(card.count)
  } else {
    store.cart.push({
      name: this.name,
      price: this.price,
      image: this.image,
      count: 1,
    });
    console.log(store.cart)
  }
},
  },
}

</script>

<style>
.card {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  width: 27vw;
  height: 65vh;
  margin: 1rem auto;
  align-items: center;
  background-color: var(--secondary);
  border: solid;
  border-radius: 1rem;
  border: 1px solid;
  color: var(--inv);
  box-shadow: var(--shadow) 0px 3px 8px;
}
.card > img {
  width: 90%;
  height: 55%;
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


body {background-color: var(--primary)}

</style>