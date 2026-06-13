<template>
    <div>
        <h1>Api Users</h1>
        <div v-for="user in users" :key="user.id">
            ID: {{ user.id }}
            Name: {{ user.name }}
            Email: {{ user.email}}
            Usernaem: {{ user.username}}

        </div>
        

    </div>

</template>


<script setup>
// https://jsonplaceholder.typicode.com/

const users = ref([])


const fetchUsers = async () => {
                        // GET reuest
    const response = await $fetch('https://jsonplaceholder.typicode.com/users')
    users.value = response
}




await fetchUsers()

</script>