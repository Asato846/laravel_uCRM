<script setup>
import { reactive } from 'vue'
import { Inertia } from '@inertiajs/inertia'

defineProps({
    errors: Object
})

const form = reactive({
    title : null,
    content : null
})

const submitFunctioin = () => {
    Inertia.post('/inertia',form)
}

</script>

<template>
    <form @submit.prevent="submitFunctioin">
        <input type="text" name="title" v-model="form.title"><br>
        <div v-if="errors.title">{{ errors.title }}</div>
        <input type="text" name="content" v-model="form.content"><br>
        <div v-if="errors.content">{{ errors.content }}</div>
        <button>send</button>
    </form>
</template>