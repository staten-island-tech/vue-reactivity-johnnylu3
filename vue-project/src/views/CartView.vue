<template>
<div class="container">
  <Cart v-for="(drink, index) in store.cart"
        :key="drink.name"
        :name="drink.name"
        :price="drink.price"
        :image="drink.image"
        :count="drink.count"
        :index="index">
        </Cart>
</div>

<div class="cart-info">
      Total price: ${{ calculateTotal() }}
        <p v-show="store.cart.length === 0">Your cart is empty.</p>
      </div>

</template>

<script>
import Cart from '../components/Cart.vue';
import { store } from '../components/store';
  export default {
    name:"CartView",
    components: {
      Cart,
    },
    data() {
        return {
            store,
        }},
    methods: {
      calculateTotal() {
        let total = 0;
      for (let i = 0; i < store.cart.length; i++) {
        total += store.cart[i].price * store.cart[i].count;
      }
      return total;
    },
  },
  
  
}
</script>

<style>
.container {
display: flex;
flex-direction: column;
flex-wrap: wrap;
justify-content: space-around;
width: 90vw;
margin: 2rem auto;}

.cart-info {
  display: flex;
  flex-direction: column;
  text-align: center;
}



</style>