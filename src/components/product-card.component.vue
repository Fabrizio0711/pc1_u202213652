<script >
import {ProductDataService} from "../services/product-data.service.js";

export default {
  name: "ProductCard",
  data(){
    return{
      datas:[],
      dataService: new ProductDataService(),
    }
  },
  beforeMount() {
    //invocar API
    this.dataService.getAll().then((response) => {
      if (response.status === 200) {
        this.datas = response.data;
      } else {
        alert("Ha ocurrido un error al obtener los datos.");
      }
    }).catch((error) => {
      alert("Ha ocurrido un error al obtener los datos: " + error.message);
    });
  }

}
</script>

<template>
<div>
  <div v-for="product in datas">
        <div  class="container">
        <p>Title: {{product.title}}</p>
        <p>Price: {{product.price}}</p>
        <p>Description: {{product.description}}</p>
        <p>Category: {{product.category}}</p>
          <img :src="product.image">
          <p>Rating: {{product.rating}}</p>
        </div>
  </div>

</div>
</template>

<style >
.container{
  border: 1px solid black;
  margin: 10px;
  padding: 10px;
  width: 300px;
  display: inline-block;
  vertical-align: top;
  text-align: left;
  background-color: #f1f1f1;
  color:black;
}
img{
  width: 100%;
  height: auto;
  margin: 10px 0;
}
</style>