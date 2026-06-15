<template>
  <n-modal
    v-model:show="modalShow"
    preset="dialog"
    title="Student Information"
    positive-text="Submit"
    @positive-click="handleClose"
    @update:show="handleUpdateShow"
  >
    <n-card>
      <p>Name: {{ studentName }}</p>
      <!-- <p>Course: {{ selectedCourse }}</p> -->
    </n-card>

  </n-modal>
</template>

<script setup>
import { NCard, NModal } from 'naive-ui';

const props = defineProps({
  show: Boolean,
  studentName: String,
  // selectedCourse: String,
})

const emit = defineEmits(['update:show'])

const modalShow = computed({
  get() {
    return props.show
  },
  set(value) {
    emit('update:show', value)
  }
})

const handleClose = () => {
  emit('update:show', false)
}
const handleUpdateShow = () => {

  emit('update:show', false)
}
</script>