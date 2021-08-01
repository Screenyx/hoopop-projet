<template>
  <div id="app">

    <nav class="navbar navbar-expand navbar-dark bg-dark">    
      <div>
        <div class="dropdown open">
          <button class="btn btn-secondary dropdown-toggle" type="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Panier(0)</button>
          <div>
              <mini-cart/>
          </div>
          
        </div>     
      </div>
    </nav>

    <img alt="Vue logo" src="./assets/logo.png">
    <h1>Liste des produits</h1>
    <br>
    <li class="liste" v-for="product in products" :key="product.productId">
      <img class="pic" :src="product.productPicture">
      {{product.productName}}
      | Prix : {{product.productPrice}} €
      <button class="btn btn-primary">+</button>
    </li>
    
  </div>
</template>

<script>

import productsData from './products.json';
import MiniCart from "./components/MiniCart.vue";


export default {
  name: 'App',
  components: { MiniCart },
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
