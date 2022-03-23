<template>

  <v-container>
    <v-row>
      <v-col cols="4" v-for="(product,idx) in products" :key="idx">
        <Product :product="product" @delete="deleteProduct" @edit="editProduct" />
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-btn color="green" @click="addProduct" >Add Product</v-btn>
      </v-col>
    </v-row>
  </v-container>

</template>

<script>
import Product from '@/components/Product';
export default {
  components: {
    Product
  },
  computed: {
    products() {
      return this.$store.state.products;
    }
  },
  created() {
    this.$store.dispatch('getProducts');
  },
  methods: {
    addProduct() {
      this.$router.push({ name: 'edit' });
    },
    async deleteProduct(product) {
      console.log('delete', product.id);
      await this.$store.dispatch('deleteProduct', product);
      this.$store.dispatch('getProducts');
    },
    editProduct(product) {
      console.log('edit', product.id);
      this.$router.push({ name: 'edit', params: {product: product} });
    }
  }
};
</script>
