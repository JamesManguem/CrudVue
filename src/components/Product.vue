<template>

  <v-card>
    <v-card-title>
      {{ product.name }}
    </v-card-title>
    <v-card-text>
      <p>
      Product Price {{ product.price }} .
      </p>
    </v-card-text>
    <v-card-actions>
      <v-btn color="red" @click="$emit('delete',product)">Delete</v-btn>
      <v-btn color="yellow" @click="$emit('edit',product)">Edit</v-btn>
    </v-card-actions>
  </v-card>

</template>

<script>
export default {
  props: ['product'], 
  data: () => ({

  }),
  created() {
    console.log('product created');
  },
  methods: {
  }
};
</script>
