<template>
  <div class="mainhost">
    <div class="container">
      <input
        class="text"
        type="text"
        placeholder="username"
      >
      <input
        class="date"
        type="date"
        placeholder="date of birth"
      >
      <button class="btn-submit"
       @click="handleSubmit">
        Submit
      </button>
      
        

    </div>
  </div>
</template>

<script setup>
    
     const router = useRouter()
     
     const handleSubmit = () => {
      router.push('/home')
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
    background: rgb(90, 20, 20);
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
    background: gray;
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