<template>
  <div>
     {{ name }} : {{ price }}
  </div>
</template>

<script setup>
defineProps({ 
  name: String,
  price: Number
})
</script>