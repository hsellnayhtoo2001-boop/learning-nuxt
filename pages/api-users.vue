<template>
    <div>
        <h1>Api Users</h1>
        <input
            v-model="searchText"
            type="text"
            placeholder="Search User Name ..."
        />

        <div
            v-for="user in users"
            :key="user.id"
        >
            <div> ID: {{ user.id }}</div>
            <div>Name: {{ user.name }}</div>
            <div>Email: {{ user.email }}</div>
            <div>Username: {{ user.username }}</div>


        </div>



    </div>

</template>


<script setup>
import { NCard } from 'naive-ui'

// https://jsonplaceholder.typicode.com/

const users = ref([])


const fetchUsers = async () => {
    // GET reuest
    const response = await $fetch('https://jsonplaceholder.typicode.com/users')
    users.value = response
}




await fetchUsers()

</script>