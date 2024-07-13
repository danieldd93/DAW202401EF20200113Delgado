<template>
  <h5>Listado de Series</h5>
  <div class="product-list">
    <div class="product-grid">
      <div class="product-item" v-for="product in products" :key="product.id">
        <ProductItem :product="product" />
      </div>
    </div>
  </div>
</template>

<style>
.product-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20xp;
}
</style>

<script>
import ProductItem from "src/components/product/ProductItem.vue";

export default {
  name: "ProductList",
  components: { ProductItem },
  data() {
    return {
      products: [],
    };
  },
  mounted() {
    this.loadProducts();
  },
  methods: {
    loadProducts() {
      var URL = "";
      var token =
        "eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJjODRmMmUwODYxM2JmN2FlYTM1OGI0OTgzNDNkMWUwNiIsInN1YiI6IjVmZTUxM2M3ZTE4Yjk3MDAzYzg5NzE3MCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.StJwmra-PsBwZTOXWg3Y06VEu8CGfAo8dXV7ZQ3RnIs";
      this.$apiProducts
        .get(URL, {
          headers: {
            Authorization: "Bearer " + token,
          },
        })
        .then((response) => {
          this.products = response.data.results;
          console.log(JSON.stringify(response.data.results));
        })
        .catch((error) => {
          console.log("Ocurrio un error: " + error);
          this.$router.push("/");
        });
    },
  },
};
</script>
