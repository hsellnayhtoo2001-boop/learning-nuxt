<template>
  <div>
    <div>
      Users
    </div>

    <!-- Looping All User -->
    <div v-for="us in users">
      Name: {{ us.name }},
       Age: {{us.age}}
    </div>


    <div style="padding-top: 30px">
      Male User
    </div>

    <!-- Display Male User using filter js -->
     <div v-for="m in maleUsers">
      Name:{{ m.name }},
      Age: {{ m.age }},
      Gender:{{ m.gender }}
     </div>
      <!-- <div v-for="m in maleUsers">
      Name: {{ m.name }}
      Age: {{ m.age }}
      Gender: {{ m.gender }}
    </div> -->
     
    <!-- Display user name only using map js -->
    <!-- <div v-for="name in usersName">
      Name: {{ name }}

    </div> -->


    <!-- Display Male User Using vif  -->
    <!-- <div v-for="u in users">
      <div v-if="u.gender == 'male'">
        Name: {{ u.name }},
        Age: {{ u.age }}

      </div>
    </div> -->



  </div>
</template>

<script setup>
  const users = [
    { id: 1, name: 'John', age: 25, gender: 'male' },
    { id: 2, name: 'Alice', age: 21, gender: 'female' },
    { id: 3, name: 'Jane', age: 23, gender: 'female' },
    { id: 1, name: 'Doe', age: 22, gender: 'male' },
  ]

  const maleUsers = users.filter(u => u.gender == 'male')
  console.log("Filtered male users", maleUsers)

  const usersName = users.map(u => u.name)
  console.log("Mapped users:", usersName)


</script>