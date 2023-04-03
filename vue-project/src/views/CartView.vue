<template>
<Cart v-for="(drink, index) in store.cart"
        :key="drink.name"
        :name="drink.name"
        :price="drink.price"
        :image="drink.image"
        :count="drink.count"
        :index="index">
        </Cart>

        Total price: ${{ calculateTotalPrice() }}
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
      calculateTotalPrice() {
      let totalPrice = 0;
      for (let i = 0; i < store.cart.length; i++) {
        totalPrice += store.cart[i].price * store.cart[i].count;
      }
      return totalPrice;

    },


  },
  
  
}
</script>

<style>

</style>