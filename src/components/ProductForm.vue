<template>
  <div class="row">
    <div class="col-sm-6 col-md-4 col-lg-4">
      <form @submit.prevent="addProduct" novalidate>
        <fieldset>
          <legend>Nuevo producto</legend>
          <!-- Aquí los inputs y botones del form -->
          <div class="form-group">
            <label>ID:</label>
            <input
              type="text"
              class="form-control"
              v-model.number="newProduct.id"
              disabled
            />
          </div>
          <div class="form-group">
            <label>Nombre:</label>
            <input
              type="text"
              class="form-control"
              v-model="newProduct.name"
              required
            />
            <span class="error"></span>
          </div>
          <div class="form-group">
            <label>Unidades:</label>
            <input
              type="number"
              class="form-control"
              min="0"
              step="1"
              v-model.number="newProduct.units"
            />
            <span class="error"></span>
          </div>
          <div class="form-group">
            <label>Precio/u.:</label>
            <input
              type="number"
              class="form-control"
              required
              min="0"
              step="0.01"
              v-model.number="newProduct.price"
            />
            <span class="error"></span>
          </div>
          <button type="submit" class="btn btn-default btn-primary">
            Añadir
          </button>
          <button type="reset" class="btn btn-danger">Reset</button>
        </fieldset>
      </form>
    </div>
  </div>
</template>

<script>
import api from "../API";
import store from "../store";

export default {
  name: "products-form",
  data() {
    return {
      newProduct: {},
    };
  },
  methods: {
    addProduct() {
      api.products
        .create(this.newProduct)
        .then(() => alert("Se añadio el producto, recarga para verlo"))
        .catch((error) => store.addMessageAction(error));
      this.newProduct = {};
    },
  },
};
</script>