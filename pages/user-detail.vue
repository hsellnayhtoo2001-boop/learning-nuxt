<template>
  <div>
    <h1>User Detail</h1>
    <p>Id: {{ id }}</p>
    <p>Name: {{ name }}</p>
    <p>Age: {{ age }}</p>
    <p>Email: {{ email }}</p>
    <p>Gender: {{ gender }}</p>
    
  </div>
</template>

<script setup lang="ts">
const route = useRoute()
const name = route.query.name
const age = route.query.age
const email = route.query.email
const gender = route.query.gender
const id = route.query.id
// const selectedUser = users.find(u => u.id == id)
</script>