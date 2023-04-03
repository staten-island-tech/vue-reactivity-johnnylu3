<template>
<Cart v-for="(drink, index) in store.cart"
        :key="drink.name"
        :name="drink.name"
        :price="drink.price"
        :image="drink.image"
        :count="drink.count"
        :index="index">
        </Cart>

        Total price: ${{ calculateTotal() }}
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

</style>