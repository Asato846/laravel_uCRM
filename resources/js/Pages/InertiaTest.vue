<script setup>
import { Head, Link } from '@inertiajs/inertia-vue3';
import { ref } from 'vue';

const newTitle=ref('')
const newContent=ref('')
</script>

<template>
    Inertia test <br>
    <a href="/">a tag</a><br>
    <Link href="/"> Link pass </Link><br>
    <Link :href="route('inertia.index')">Confirm to named Route</Link><br>
    <Link :href="route('inertia.show', { id: 1 })">Confirm to named Route and Param</Link><br>

    <div class="mb-8"></div>
    <input type="text" name="newTitle" v-model="newTitle"></input><br>
    <input type="text" name="newContent" v-model="newContent"></input><br>
    <Link as="button"  method="post" :href="route('inertia.store')"
    :data="{
        title: newTitle,
        content: newContent
    }">store DB</Link>
</template>