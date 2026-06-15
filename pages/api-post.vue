<template>
    <div>
      <h2>Api Post</h2>
      {{ posts }}
    </div>
</template>

<script setup>
  const posts = ref ([])

  const fetchPosts = async () => {
      const response = await $fetch('https://jsonplaceholder.typicode.com/posts')
      posts.value = response 
      console.log("postName", response)
  }
   


  await fetchPosts()
  console.log("post", posts.value )
</script>