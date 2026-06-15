<template>
    <div class="container">
        <div class="sub-container">
            <n-space vertical>
                <n-input
                    v-model:value="name"
                    type="text"
                    placeholder="Enter student name"
                />
                <n-select
                    v-model:value="selectedCourse"
                    :options="courseOptions"
                />
                <n-button
                    tertiary
                    type="primary"
                    @click="handleSubmit"
                >
                    Submit
                </n-button>
            </n-space>
        </div>



    </div>
    <student-dialog
        v-model:show="showModal"
        :student-name="name"
    />
</template>

<script setup>
import { NSpace, NInput, NSelect, NButton } from 'naive-ui';
import StudentDialog from '~/components/StudentDialog.vue';


const name = ref(null)
const selectedCourse = ref('')
const showModal = ref(false)
const courseOptions = [
    {
        label: "Nuxt Beginner",
        value: 1
    },
    {
        label: "Vue Basic",
        value: 2
    },
    {
        label: "Frontend Starter",
        value: 3
    }
]

const handleSubmit = () => {
    console.log("name", name.value)
    console.log("selected courese", selectedCourse.value)
    showModal.value = true
}

</script>

<style lang="css">
.container {
    display: flex;
    justify-content: center;
    padding: 20px;
}

.sub-container {

    width: 300px;
}
</style>