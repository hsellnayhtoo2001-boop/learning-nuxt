<template>

  <div
    v-for="usr in users"
    :key="usr.id"
  >
    <UserCard
      :user="usr"
      @clicked-user="handleUserClick"
      @deleted-user="handleDelete"
    />
  </div>
</template>


<script
  setup
  lang="ts"
>
  import type { UserType } from '~/components/UserCard.vue';

  const router = useRouter() 
  const users = ref([
    {
      id: 1,
      name: 'John',
      age: 25,
      gender: 'male',
      email: 'john@gmail.com',
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

  // when user card is clicked, redirect to the user-detail page with user data
  const handleUserClick = (user: UserType) => {
    console.log(user)
    router.push({
        path: '/user-detail',
        query: {
          id: user.id,
          name: user.name,
          age: user.age,
          gender: user.gender,  
          email: user.email
        }
      })
  }

  const handleDelete = (user: UserType) => {
    users.value = users.value.filter((usr) => usr.id != user.id)
  }

</script>