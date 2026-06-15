<template>
  <div>
    Welcome our website, {{ loggedinUsername }}.
    Your's BIO, {{ loggedinBio }}

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

    <NuxtLink
      style="padding-bottom:30px"
      to="/api-users"
    >
      Api User
    </NuxtLink>
  
    <NuxtLink
      style="padding-bottom:30px"
      to="/api-post"
    >
       Api Posts
    </NuxtLink>

    <NuxtLink
      style="padding-bottom:30px"
      to="/naive-ui-demo"
    >
       Naive UI demo
    </NuxtLink>

 
  </div>

</template>

<script setup>

const route = useRoute();

const loggedinUsername = route.query.username

const loggedinBio =route.query.Bio

</script>