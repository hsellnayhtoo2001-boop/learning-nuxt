<template>
  <div>
    <div>
      Current count: {{ count }}
    </div>
  <div>
     <button @click="handleAdd">Add +</button>
    </div>
      <div> 
    <div style="padding-top: 40px;">
      Decrease count: {{ decrease }} 
    </div>
    <div>
      <button @click="handleLoss">Less -</button>
    </div>
  </div>
  </div>

</template>

<script setup>
  const count = ref(0);

  const handleAdd = () => {
    count.value = count.value + 1
  }
  const decrease = ref(100);

  const handleLoss = () => {
    decrease.value = decrease.value - 1
  }
</script>