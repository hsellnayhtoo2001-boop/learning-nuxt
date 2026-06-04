<template>
  <div v-for="p in products">
    <Product :product="p" />

    <!-- <Product
      :name="p.name"
      :price="p.price"
    /> -->
  </div>
  <br>
  <div v-for="e in electronicsProducts">
    <Product :product="e" />

    <!--
      <Product
      :name="e.name"
      :price="e.price"
    /> -->

  </div>
</template>


<script setup>

  const products = [
    { id: 1, name: 'Laptop', price: 1200, category: 'Electronics' },
    { id: 2, name: 'Keyboard', price: 50, category: 'Electronics' },
    { id: 3, name: 'Notebook', price: 5, category: 'Stationery' },
    { id: 4, name: 'Pen', price: 2, category: 'Stationery' },
    { id: 5, name: 'Monitor', price: 300, category: 'Electronics' },
  ]

  const productsName = products.map(p => p.name)
  console.log("Mapped products:", productsName)

  const electronicsProducts = products.filter(p => p.category == 'Electronics')
  console.log("Filtered Electronics products", electronicsProducts)

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