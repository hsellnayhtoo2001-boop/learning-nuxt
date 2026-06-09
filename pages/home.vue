<template>
  <div>
    Welcome our website, {{ loggedinUsername }}

  </div>
  <div style="display: flex; flex-direction: column; padding: 30px">
    <NuxtLink
      style="padding-bottom:30px"
      to="/counter"
    >
      Counter
    </NuxtLink>

    <NuxtLink
      style="padding-bottom:30px"
      to="/about"
    >
      About
    </NuxtLink>

    <NuxtLink
      style="padding-bottom:30px"
      to="/products"
    >
      Products
    </NuxtLink>
    <NuxtLink
      style="padding-bottom:30px"
      to="/users"
    >
      User
    </NuxtLink>

  </div>


</template>

<script setup>

const route = useRoute();

const loggedinUsername = route.query.username

</script>