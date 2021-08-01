<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Liste des produits</h1>
    <button type="button">Valider le panier</button>
    <br>
    <li class="liste" v-for="product in products" :key="product.productId">
      <img class="pic" :src="product.productPicture">
      {{product.productName}}
      
      <button>+</button>
    </li>
    
  </div>
</template>

<script>

import productsData from './products.json'

export default {
  name: 'App',
  components: {
    
  },
  data() {
    return {
      products: productsData,
    };
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.liste {
  text-align: left;
  padding-top: 20px;
  list-style: none;
  display: inline-block
}
.pic {
  height: 100px;
  padding: 20px;
  vertical-align: middle;
}
</style>
