<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>



<template>
  <header>
    <div class="wrapper">
      <h1 class="title">Bev</h1>
      <nav>
        <RouterLink to="/">Menu</RouterLink>
        <RouterLink to="/about">Cart</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
.title { 
  text-align: center;

}
.wrapper {
  text-align: center;
  width: 100vw;
}
.title {
  font-size: 50px;
  text-align: center;
  width: 100vw;
}
header {
  line-height: 1.5;
  max-height: 100vh;
  text-align: center;
}
nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}
nav a.router-link-exact-active {
  color: var(--color-text);
}
nav a.router-link-exact-active:hover {
  background-color: transparent;
}
nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}
nav a:first-of-type {
  border: 0;
}
@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
  .logo {
    margin: 0 2rem 0 0;
  }
  header .wrapper {
    display: flex;
    place-items: center;
    flex-wrap: wrap;
  }
  nav {
    text-align: center;
    font-size: 1rem;
    padding: 1rem 0;
    margin-top: 1rem;
  }}
</style>
