<template>
  <div 
  class="child"
  @click="handleClick(product)" >
    <!-- {{ name }} : {{ price }} -->
    <div>
      Name: {{ product.name }}
    </div>
     <div>
      Price: {{ product.price }}
    </div>
     <div>
      category: {{ product.category }}
    </div>
  
    </div>

</template>

<script
  setup
  lang="ts"
>

export type ProductType = {
    id: Number,
    name: String,
    price: Number,
    category: String
  }


  const props = defineProps<{
    product: ProductType
  }>()


  const emit = defineEmits(['clicked-product'])

  const handleClick =(product: ProductType) => {
    console.log("Clicked product", product)
    emit('clicked-product', product)
  }
  // defineProps({
  // name: String,
  // price: Number
  
  // })
</script>

<style>
.child {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
    padding: 20px;
    width: 300px;
    background: rgb(28, 147, 134);
}

</style>