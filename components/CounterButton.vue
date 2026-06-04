<template>
  <div>{{ title }}: {{ count }}</div>
  <button @click="handleClick">
    {{ buttonText }}
  </button>

</template>

<script setup>
  const props = defineProps({
    title: String,
    count: Number,
    buttonText: String,
  })

  const emit = defineEmits(['change-count'])

  const handleClick = () => {
    emit('change-count')
  }

</script>