<template>
    <div>
        <h2 v-for="table in tables" :key="table">{{ table }}</h2>
    </div>
</template>

<script setup>
const tables = ['a1', 'a2', 'a3']
</script>

<style scoped>

</style>