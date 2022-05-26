<script setup>
    import { ref, onMounted } from 'vue'
    import Modal from './Modal.vue'

    const dateString = ref('')
    const isModalVisible = ref(false)

    onMounted(() => {
        dateString.value = new Date().toLocaleDateString()
        console.log(`The initial count is ${dateString.value}.`)
    })

    const openCalendar = () => {
        isModalVisible.value = true
    }

    const closeCalendar = () => {
        isModalVisible.value = false
    };

</script>

<template>
    This is a calendar
    <input type="" v-model="dateString" @click="openCalendar" />

    <Modal 
        v-show="isModalVisible"
        @close="closeCalendar"
    />
</template>