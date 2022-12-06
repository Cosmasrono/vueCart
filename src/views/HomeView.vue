<script setup> 
</script>

<template>
<main> 
  <button v-on:click="navigateTo('product')">view product</button>
  <header>{{cart.length}} products in cart
    <button v-on:click="navigateTo('cart')">view cart</button>
  </header>
  {{pages}}

  <div v-if="page=='cart'">
    <h1>your cart</h1>
    <div class="products">
    <div
   v-for="product in cart"
  :key="product"> 
  <img :src=" product.image" > 
  {{product.name}}
  
  <div>{{product.cost}}
  </div>
  <button v-on:click="removeItemFromCart(product)" class="p-5 ml-20 text-white rounded-md bg-slate-900">add to cart
    </button>
    </div>
  </div>
  </div>

  <div v-if="page=='products'">
    <h1>products</h1>
  

  <div class="products">
    <div
   v-for="product in products"
  :key="product"> 
  <img :src=" product.image" > 
  {{product.name}}
  
  <div>{{product.cost}}
  </div>
  <button v-on:click="addItemToCart(product)" class="p-5 ml-20 text-white rounded-md bg-slate-900">remove item
    </button>
    </div>
  </div>
  </div>
    
</main>
</template>
<script>
export default {
  name:"app",
  data(){
    return{
      page:'products',
      cart:[],
      
    products:[
      {
        id:'1',
        name:"cosmas",
        cost:"500",
        image:"https://cdn.pixabay.com/photo/2022/11/30/22/19/cottage-7627904__340.jpg"
      },
      {
        id:'1',
        name:"cosmas",
        cost:"500",
        image:"https://cdn.pixabay.com/photo/2022/11/30/22/19/cottage-7627904__340.jpg"
      },
      {
        id:'1',
        name:"cosmas",
        cost:"500",
        image:"https://cdn.pixabay.com/photo/2022/11/30/22/19/cottage-7627904__340.jpg"
      },
      {
        id:'1',
        name:"cosmas",
        cost:"500",
        image:"https://cdn.pixabay.com/photo/2022/11/30/22/19/cottage-7627904__340.jpg"
      },
    ]

  };

  },
  methods:{
    addItemToCart(product){
      this.cart.push(product)
    },
  navigateTo(page){
    this.page=page;
  }
},
removeItemFromCart(product){
this.cart.splice(this.cart.indexOf(product))
},
components:{}
};
</script>

<style>

</style>
