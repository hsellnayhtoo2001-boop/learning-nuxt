<template>
  <div
    @click="handleClick(user)"
    style="margin-bottom: 10px; width: 300px; background-color: #efefef; padding: 20px;"
  >
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
  const emit = defineEmits(['clicked-user'])

  const handleClick = (user: UserType) => {
    console.log("Clicked user", user)
    emit('clicked-user', user)
  }


</script>