<template>




  <v-card>
    <table class="table table-striped">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Product Name</th>
      <th scope="col">Product price</th>
      
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">{{product.id}}</th>
      <td>  {{ product.name }}</td>
      <td>{{ product.price }}</td>
      <td><v-btn color="red" @click="$emit('delete',product)">Delete</v-btn>
      <v-btn color="yellow" @click="$emit('edit',product)">Edit</v-btn></td>
    </tr>
  </tbody>
</table>
    
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
