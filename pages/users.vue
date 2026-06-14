<template>
<h2>Users Page</h2>
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
  <input 
  v-model="searchText"
  type="text"
  placeholder="Search User ..."
  />
  <button 
    style="padding: 4 10px; margin:0 20px 20px 20px;"
    @click="selectedGender = 'All'"
  >All </button>
  <button 
  style="margin-right: 20px"
  @click="selectedGender = 'male'">Male</button>
  <button 
  style="margin-right: 20px"
  @click="selectedGender = 'female'">Female</button>

  <p v-if="selectedGender" !="All">Current filter is {{ selectedGender }}</p>


  <div v-for="u in searchUsers" :key="u.id">
    <div style="background-color: rgb(28, 147, 134); width: 300px; ">
      <p>Name:{{ u.name }}</p>
      <p>age:{{ u.age }}</p>
      <p>gender:{{ u.gender }}</p>
    </div>
  </div>
  <div v-for="u in filteredUsers"
  :key="u.id">
  <UserCard
    :user="u"
    @clicked-product="handleUserClicked"
    />

  </div>
</template>


<script
  setup
  lang="ts"
>
  // import { u, U } from 'vue-router/dist/useApi-D6ckOsFy.js'
  import type { UserType } from '~/components/UserCard.vue';

  
  const selectedGender = ref('All')
  const searchText = ref('')
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
  const searchUsers = computed(() => {
    if (searchText.value === ''){
      return users.value
    }
        return users.value.filter((user) => user.name.toLocaleLowerCase().includes(searchText.value.toLocaleLowerCase()))

  })
  const filteredUsers = computed(() => {
    if (selectedGender.value === 'All'){
      return users.value
    }
    return users.value.filter((u) => u.gender == selectedGender.value)
  }
)
   const handleUserClicked = (users: UserType) => {
   }

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