<template>
  <div
    
    style="margin-bottom: 10px; width: 300px; background-color: #efefef; padding: 20px;"
  >
   <div @click="handleClickDiv(user)">
      <div>
        Name: {{ user.name }}
      </div>
      <div>
        Age: {{ user.age }}
      </div>
      <div>
        Email: {{ user.email }}
      </div>
      <div>
        Gender: {{ user.gender }}
      </div>
    </div>

  <button @click="handleDelete(user)">
    Delete
  </button>
  </div>


</template>


<script
  setup
  lang="ts"
>

  // declare type using typescript
  export type UserType = {
    id: Number,
    name: String,
    age: Number,
    gender: String,
    email: String
  }


  // props 
  const props = defineProps<{
    user: UserType
  }>()

  // console.log("Received user", props.user.name)


  // emit 
  const emit = defineEmits(['clicked-user', 'deleted-user'])

  const handleClickDiv = (user: UserType) => {
    console.log("Clicked user", user)
    emit('clicked-user', user)
  }

  const handleDelete = (user: UserType) => {
    emit('deleted-user', user)
  }


</script>