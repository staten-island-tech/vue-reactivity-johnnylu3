<template>
<div class="card-container"><Card   v-for="drink in drinks"
        :key="drink.name"
        :name="drink.name"
        :type="drink.type"
        :price="drink.price"
        :image="drink.img"></Card>
        </div>
</template>

<script>
import Card from '../components/Card.vue';
import { store } from '../components/store';

  export default {
  name: "HomeView",
  components: {
    Card
  },
    data() {
        return {
            store,
            drinks: [
                {
                    name: "water",
                    type: "water",
                    price: 2,
                    img: "https://cbss.co.za/wp-content/uploads/2021/11/CBSS-Square-Image-8.jpg",
                },
                {
                    name: "sparkling water",
                    hotorcold: "cold",
                    type: "water",
                    price: 2,
                    img: "https://whitewaternow.com/wp-content/uploads/2018/06/drinking-sparkling-water-side-effects.jpg",
                },
                {
                    name: "coke",
                    hotorcold: "cold",
                    type: "soda",
                    price: 4,
                    img: "https://images.english.elpais.com/resizer/R6YspvxWIe0hgJtDRo4o1GNvyMQ=/1960x1103/cloudfront-eu-central-1.images.arcpublishing.com/prisa/LMOKDYNLMD64ZCSK4YL23ELEGY.jpg",
                },
                {
                    name: "sprite",
                    hotorcold: "cold",
                    type: "soda",
                    price: 4,
                    img: "https://editors.dexerto.com/wp-content/uploads/2022/04/18/TikTokSpriteChallenge.jpg",
                },
                {
                    name: "orange juice",
                    hotorcold: "cold",
                    type: "juice",
                    price: 6,
                    img: "https://salimaskitchen.com/wp-content/uploads/2022/01/Fresh-Squeezed-Orange-Juice-Salimas-Kitchen-20.jpg",
                },
                {
                    name: "apple juice",
                    hotorcold: "cold",
                    type: "juice",
                    price: 6,
                    img: "https://i0.wp.com/nycstreetgrill.com/wp-content/uploads/2019/08/glass-of-apple-juice-with-slices-of-red-apple-vector-18547427-copy.jpg?fit=1000,1004&ssl=1",
                },
                {
                    name: "coffee",
                    type: "coffee",
                    price: 8,
                    img: "https://images.pexels.com/photos/312418/pexels-photo-312418.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500",
                },
                {
                    name: "ginger tea",
                    type: "tea",
                    price: 6,
                    img: "https://detoxinista.com/wp-content/uploads/2020/10/ginger-tea-recipe.jpg",
                },
            ],
        };
    },
    methods: {},
}
</script>

<style>

.card-container {

  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
  width: 90vw;
  margin: 2rem auto;}


</style>