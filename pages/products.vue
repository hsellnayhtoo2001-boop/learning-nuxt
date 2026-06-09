<template>
  <div>Product page</div>
  <div v-for="p in products"
  :key="p.id">

    <Product
      :product="p"
      @clicked-product="handleProductClick"
    />
  </div>
 
</template>


<script 
  setup
  lang="ts"
>
  import type { ProductType } from '~/components/Product.vue'

  const products = ref( [
    { 
      id: 1,
      name: 'Laptop',
      price: 1200,
      category: 'Electronics'
     },
    { 
      id: 2,
      name: 'Keyboard',
      price: 50,
      category: 'Electronics'
     },
    { 
      id: 3,
      name: 'Notebook',
      price: 5,
      category: 'Stationery' 
     },
    { 
      id: 4,
      name: 'Pen',
      price: 2,
      category: 'Stationery'
      },
    {
      id: 5,
      name: 'Monitor',
      price: 300,
      category: 'Electronics'
       },
    ])
  

  const handleProductClick =(product: ProductType) =>{
    products.value = products.value.filter((p) => p.id !=product.id)
  }  
</script>


<!-- <template>
  <div>

    <div style="padding-top:40px">
      Products
    </div>
    <!-- Show all products name  -->


<!-- <div v-for="p in products">
      <Product :name="p" />
      Name:{{
        p.name
      <!-- }}
    </div> -->

<!-- </div>

  <div>
    <div style="padding-top:40px">
      Electronics name
    </div>
    <div v-for="e in electronicsProducts">
      Name:{{ e.name }}

    </div>
    <!-- Show only electronics name -->
<!-- 
  </div> -->
<!-- </template>-->