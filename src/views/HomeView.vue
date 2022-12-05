<script setup>
</script>

<template>
<main>
<h1>products</h1>
    <div class=""
   v-for="product in products"
  :key="product">{{product.name}}
  <img :src=" product.image" >
  <div>{{product.cost}}
  </div>
  <button v-on:click="addItemToCart(product)">add to cart
    </button>
    </div>
</main>
</template>
<script>
export default {
  name:"app",
  data(){
    return{
    products:[
      {
        id:'1',
        name:"cosmas",
        cost:"500",
        image:"https://cdn.pixabay.com/photo/2022/11/30/22/19/cottage-7627904__340.jpg"
      }
    ]

  }

  },
  methods:{
    addItemToCart(product){
      console.log(product);
    }
  }
}
</script>

<style>

</style>
