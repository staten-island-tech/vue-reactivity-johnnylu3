<template>
    <div class="Cart-card">
      <img :src="image" :alt="name" />
      <h3>{{ name }}</h3>
      <p>{{ price }}</p>
      <p>Count: {{ count }}</p>
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
      },
  methods: {
    removeFromCart() {
    if (this.count === 1) {
      store.cart.splice(this.index, 1);
    } else {
      this.count--;
    }
  },
}
  }

</script>

<style scoped>

</style>