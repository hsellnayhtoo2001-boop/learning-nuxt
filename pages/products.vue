<template>
  <h2>Product page</h2>

  <input
    v-model="searchText"
    type="text"
    placeholder="Search product ..."
  />


  <button 
    style="padding: 4 10px; margin:0 20px 20px 20px;"
    @click="selectedCategory = 'All'"
  >
      All
  </button>
  <button
    style="margin-right: 20px"
    @click="selectedCategory = 'Electronics'"
  >
    Electronics
  </button>
  <button @click="selectedCategory = 'Stationery'">
    Stationary
  </button>

  <p v-if="selectedCategory != 'All'">Current filter is {{ selectedCategory }}</p>


  <!-- Computed For search -->
  <!-- <div v-for="p in searchProducts" :key="p.id">
    <div style="background-color: rgb(28, 147, 134); width: 300px; ">
      <p>Name: {{ p.name }}</p>
      <p>Category: {{ p.category}}</p>
      <p>Price: {{ p.price}}</p>
    </div>
  </div> -->
 

  <!-- Computed for filter buttons -->
  <div v-for="p in filteredProducts"

  :key="p.id">

    <Product
      :product="p"
      @clicked-product="handleProductClick"
    />
  </div>
  <div
  v-for="p in products"
  :key="p.id"
  >
  <Product
  :product="p"
  @clicked-product="handleProductClick"
  @deleted-product="handleDelete"
  />
</div>
 
</template>


<script 
  setup
  lang="ts"
>

  import type { ProductType } from '~/components/Product.vue'


  const selectedCategory = ref('All')
  const searchText = ref('')

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


  // Computed for search
  const searchProducts = computed(() => {
    if (searchText.value === '') {
      return products.value
    }

    return products.value.filter((product) => product.name.toLocaleLowerCase().includes(searchText.value.toLocaleLowerCase()))
  })

  // Comupted for filter
  const filteredProducts = computed(() => {
    if(selectedCategory.value == 'All') {
      return products.value
    }

    return products.value.filter((p) => p.category == selectedCategory.value)
  })
  

  // watch(searchText, (newValue, oldValue) => {
  //   console.log("Old value", oldValue)
  //   console.log("new Value", newValue)

  //   if(newValue == '') {
  //     searchText.value = ''
  //     return
  //   }

  //   searchText.value = 'You are searching for' + newValue
  // })



  // Delete function 
  const handleProductClick =(product: ProductType) =>{
  }  
  const handleDelete = (product: ProductType) => {
  products.value = products.value.filter((p) => p.id !== product.id)
}
</script>
