<template>
      <div class="card">
        <img :src="image" :alt="name" />
        <h2>{{ name }}</h2>
        <p>{{ type }}</p>
        <p>Price: ${{ price }}</p>
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
  height: fit-content;
  display: flex;
  flex-direction:column ;
  padding: 1rem 1rem 2rem;
  background: #fff1ff;
  box-shadow: 0 0 40px rgba(0, 0, 0, 0.2), 0 0 40px rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  margin-bottom: 30px;
}
.card > img {
  width: 100%;
  height: auto;
}

</style>