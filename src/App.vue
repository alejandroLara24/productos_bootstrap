<template>
  <app-nav></app-nav>
  <div class="container">
    <header>
      <h1>Almacén central de productos - ACME SL</h1>
    </header>
    <error-messages></error-messages>
    <products-table></products-table>
    <product-form></product-form>
  </div>
</template>

<script>
import AppNav from "./components/AppNav.vue";
import ProductsTable from "./components/ProductsTable.vue";
import ProductForm from "./components/ProductForm.vue";
import ErrorMessages from "./components/ErrorMessages.vue";

export default {
  name: "App",
  components: {
    AppNav,
    ProductsTable,
    ProductForm,
    ErrorMessages,
  },
};
</script>

<style>
@import url("https://cdn.jsdelivr.net/npm/bootstrap-icons@1.7.2/font/bootstrap-icons.css");

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
