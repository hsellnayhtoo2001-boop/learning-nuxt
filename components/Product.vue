<template>
  <div>
    <!-- {{ name }} : {{ price }} -->
    {{ product.name }} : {{ product.price }}
  </div>
</template>

<script
  setup
  lang="ts"
>

  type ProductType = {
    id: Number,
    name: String,
    price: Number,
    category: String
  }


  defineProps<{
    product: ProductType
  }>()


  // defineProps({
  // name: String,
  // price: Number
  
  // })
</script>