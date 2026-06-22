<template>
    <div>
        <h1>Api Users</h1>
        <n-input
            v-model:value="searchText"
            type="text"
            placeholder="Search User Name ..."
            autosize
            style="min-width: 50%"
        />

        <!-- <div
            v-for="user in users"
            :key="user.id"
        >

            <n-card>
                <h2> ID: {{ user.id }}</h2>
                <div>Name: {{ user.name }}</div>
                <div>Email: {{ user.email }}</div>
                <div>Username: {{ user.username }}</div>
            </n-card>

        </div> -->
        <div
            v-for="user in searchUsers"
            :key="user.id"
        >

            <n-card>
                <h2> ID: {{ user.id }}</h2>
                <div>Name: {{ user.name }}</div>
                <div>Email: {{ user.email }}</div>
                <div>Username: {{ user.username }}</div>
            </n-card>

        </div>





    </div>

</template>


<script setup>
import { NCard, NInput, NButton } from 'naive-ui'

// https://jsonplaceholder.typicode.com/

const users = ref([])
const searchText = ref('')

const fetchUsers = async () => {
    // GET reuest
    const response = await $fetch('https://jsonplaceholder.typicode.com/users')
    users.value = response
}
const searchUsers = computed(() => {
    if (searchText.value === '') {
        return users.value
    }
    return users.value.filter((user) => user.name.toLocaleLowerCase().includes(searchText.value.toLocaleLowerCase()))

})




await fetchUsers()

</script>