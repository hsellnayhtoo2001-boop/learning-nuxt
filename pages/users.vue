<template>
  <div
    v-for="usr in users"
    :key="usr.id"
  >
    <UserCard
      :user="usr"
      @clicked-user="handleUserClick"
    />
  </div>
</template>


<script
  setup
  lang="ts"
>
  import type { UserType } from '~/components/UserCard.vue';


  const users = ref([
    {
      id: 1,
      name: 'John',
      age: 25,
      gender: 'male',
      email: 'john@gmail.com'
    },
    {
      id: 2,
      name: 'Alice',
      age: 21,
      gender: 'female',
      email: 'alice@gmail.com'
    },
    {
      id: 3,
      name: 'Jane',
      age: 23,
      gender: 'female',
      email: 'jane@gmail.com'
    },
    {
      id: 4,
      name: 'Doe',
      age: 22,
      gender: 'male',
      email: 'doe@gmail.com'
    },
  ])

  const handleUserClick = (user: UserType) => {
    users.value = users.value.filter((u) => u.id != user.id)
  }

</script>