<template>
  <div>
    <h2>Api Post</h2>
    <n-input
      v-model:value="searchText"
      type="text"
      placeholder="Search User Name ..."
      autosize
      style="min-width: 50%"
    />
    <!-- <div
      v-for="posts in posts"
      :key="posts.id"
    >
      <n-card style="margin: 50px;">
        <div>User ID:{{ posts.userId }}</div>
        <div>ID: {{ posts.id }}</div>
        <div>Title : {{ posts.title }}</div>
        <div>Body : {{ posts.body }}</div>
      </n-card>
    </div> -->
    <div
      v-for="posts in searchUserId"
      :key="posts.id"
    >

      <n-card style="margin: 50px;">
        <div>User ID:{{ posts.userId }}</div>
        <div>ID: {{ posts.id }}</div>
        <div>Title : {{ posts.title }}</div>
        <div>Body : {{ posts.body }}</div>
      </n-card>

    </div>




  </div>
</template>

<script setup>
import { NCard, NInput } from 'naive-ui'
const posts = ref([])
const searchText = ref('')

const fetchPosts = async () => {
  const response = await $fetch('https://jsonplaceholder.typicode.com/posts')
  posts.value = response
  console.log("postName", response)
}
const searchUserId = computed(() => {
  if (searchText.value === '') {
    return posts.value
  }
  return posts.value.filter((posts) => posts.body.toLocaleLowerCase().includes(searchText.value.toLocaleLowerCase()))
})


await fetchPosts()
console.log("post", posts.value)
</script>