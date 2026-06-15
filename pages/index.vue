<template>
  <div class="mainhost">
    <div class="container">

      <div> Username is: {{ username }} </div>
      <div> BIO  is: {{ Bio }}</div>
      
      <input
        v-model="username"
        class="text"
        type="text"
        placeholder="Enter your username"
      >

      <!-- Create bio input -->
      <input 
        v-model="Bio"
        class="bio"
        type="text"
        placeholder="Enter your Bio"
      >

      <input
        v-model="password"
        class="date"
        type="password"
        placeholder="Enter your password"
      >

      <p v-if="errorMessage" style="color: #B71C1C">

        {{ errorMessage }}

      </p>
      <button class="btn-submit"
       @click="handleSubmit">
        Submit
      </button>
      
        

    </div>
  </div>
</template>

<script setup>
import { setBlockTracking } from 'vue'


    const router = useRouter()
    const errorMessage = ref('')
    const username = ref('')
    const Bio = ref('')
    const password = ref('')
     
     
     const handleSubmit = () => {
      if(username.value === '') {
        errorMessage.value = "Please enter your username"
        return
      }
      if(password.value === ''){
        errorMessage.value = "Please enter your password"
        return
      }
      if(Bio.value === ''){
        errorMessage.value = "Please enter your BIOS"
        return
      }

      // validate password

      // validate bio


      router.push({
        path: '/home',
        query: {
          username: username.value,
          // remove password and send bio
          Bio: Bio.value
        }
      })

      // router.push('/home')
     }
   
  // const router = useRouter()

  // const handleSubmit = () => {
  //   router.push('/counter')
  // }

</script>

<style>
  .mainhost {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: rgb(68, 165, 225);
  }

  .text {
    margin: 15px;
  }

  .date {
    margin: 15px;
  }

  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: rgb(128, 128, 128);
    height: 400px;
    width: 500px;

  }

  .btn-submit {
    background: red;
    padding: 5px;
    margin: 15px;
  }
</style>



<!-- <template>
  <div class="container">
    <input
      type="text"
      placeholder="username"
    >
    <button class="btn-submit">Submit</button>
  </div>
</template>

<script>
</script>


<style>
  .container {
    /* background: green; */
  }

  .btn-submit {
    background: red;
    padding: 5px;
  }
</style> -->