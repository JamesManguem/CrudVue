<template>
  <div>

    <v-form>
      <v-container>
        <v-row>
          <v-col>
            <v-text-field v-model="product.name" label="Name" required />
          </v-col>
          <v-col>
            <v-text-field v-model="product.price" label="price" required type="numeric" min="0" max="30" />
          </v-col>
        </v-row>
        <v-row>
          <v-col>
            <v-btn color="green" @click="save">Save info</v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-form>

  </div>
</template>

<script>

export default {
  data() {
    return {
      cat:null
    }
  },
  created() {
    if(this.$route.params.product) {
      this.product = this.$route.params.product;
    } else {
      this.product = {  name:'',  price: 0 };
    }
  },
  methods: {
    async save() {
      await this.$store.dispatch('saveProduct', this.product);
      console.log('back');
      this.$router.push('/');
    }
  }
};
</script>