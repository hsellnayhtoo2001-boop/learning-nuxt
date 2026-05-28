<template>
  <div>
    <div>
      Current count: {{ count }}
    </div>
  <div>
     <button @click="handleAdd">Add +</button>
    </div>
  </div>

</template>

<script setup>
  const count = ref(0);

  const handleAdd = () => {
    count.value = count.value + 1
  }
</script>

<!-- <template>
  <div>
    <div>
      Current count: {{ count }}
    </div>
    <div>
      <button @click="handleAdd"> Add + </button>
    </div>
  </div>

</template>

<script setup>
  const count = ref(0);

  const handleAdd = () => {
    count.value = count.value + 1
  }

</script> -->