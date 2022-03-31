<template>
  <div class="container">
    <div class="row">
      <b
        ><router-link :to="{ name: 'Create' }" class="b3"
          >Add New</router-link
        ></b
      >
      <table class="table">
        <thead>
          <tr>
            <th>Product Name</th>
            <th>Price</th>
            <th class="has-text-centered">Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in items" :key="item.product_id">
            <td>{{ item.product_name }}</td>
            <td>{{ item.product_price }}</td>
            <td class="has-text-centered">
              <b class="b b2"
                ><router-link
                  :to="{ name: 'Edit', params: { id: item.product_id } }"
                  class="is-info is-small"
                  >Edit</router-link
                ></b
              >
              <b
                class="button is-danger is-small b b1"
                @click="deleteProduct(item.product_id)"
                >Delete</b
              >
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
 
<script>
// import axios
import axios from "axios";

export default {
  name: "ProductList",
  data() {
    return {
      items: [],
    };
  },

  created() {
    this.getProducts();
  },

  methods: {
    // Get All Products
    async getProducts() {
      try {
        const response = await axios.get("http://localhost:5000/products");
        this.items = response.data;
      } catch (err) {
        console.log(err);
      }
    },

    // Delete Product
    async deleteProduct(id) {
      try {
        await axios.delete(`http://localhost:5000/products/${id}`);
        this.getProducts();
      } catch (err) {
        console.log(err);
      }
    },
  },
};
</script>
 
<style>
thead,
tr,
tbody,
th,
td {
  border: 1px solid black;
}
b {
  /* Green */
  border: none;
  color: white;
  padding: 4px 8px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 14px;
  margin: 4px 2px;
  transition-duration: 0.4s;
  cursor: pointer;
}
.b1 {
  background-color: white;
  color: black;
  border: 2px solid #f44336;
}

.b1:hover {
  background-color: #f44336;
  color: white;
}
.b2 {
  background-color: white;
  color: black;
  border: 2px solid #008cba;
}

.b2:hover {
  background-color: #008cba;
  color: white;
}
.b3 {
  background-color: white;
  color: black;
  border: 2px solid #f96332;
}

.b3:hover {
  background-color: #f96332;
  color: white;
}
</style>