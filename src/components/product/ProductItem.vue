<template>
  <q-card class="product-card">
    <q-card-section>
      <q-img :src="this.imageURL" alt="Imagen del producto" class="imgURL" />
    </q-card-section>
    <q-card-section>
      <q-card-title>{{ product.original_name }}</q-card-title>
      <div class="text-left">
        <q-btn
          color="yellow-9"
          icon="star"
          :label="product.vote_average"
        ></q-btn>
      </div>
      <div class="text-left">
        <q-btn color="primary" icon="book" :label="product.vote_count"></q-btn>
      </div>
    </q-card-section>
  </q-card>
</template>

<style>
.product-card {
  width: 300px;
}
.product-card q-card-section {
  height: 100px;
  overflow: hidden;
}
</style>

<script>
export default {
  name: "ProductItem",
  data() {
    return {
      imageURL: "http://image.tmdb.org/t/p/w500/" + this.product.poster_path,
    };
  },
  props: {
    product: {
      type: Object,
      required: true,
    },
  },
};
</script>
