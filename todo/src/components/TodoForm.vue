<script setup lang="ts">
    import { ref } from 'vue'

    const emit = defineEmits(['create'])
    const name = ref('')

    const add = (e) => {
        emit('create', name.value)
        name.value = ''
}
</script>

<template>
    <form @submit.prevent="add">
        <input type="text" v-model="name" placeholder="Todo name..." />
        <input type="submit" value="Add"/>
    </form>
</template>

<style scoped>
    button {
        margin-left: .5rem
    }
</style>