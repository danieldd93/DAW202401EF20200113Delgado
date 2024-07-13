<template>
  <div class="product-page">
    <div class="product-list q-mr-md">
      <ProductList />
    </div>
  </div>
</template>
<style>
.product-page {
  display: flex;
  justify-content: space-between;
}

.product-filter {
  width: 25%;
}

.product-list {
  width: 75%;
}
</style>
<script>
import ProductList from "src/components/product/ProductList.vue";

export default {
  name: "ProductPage",
  components: {
    ProductList,
  },
};
</script>
