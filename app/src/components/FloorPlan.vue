<template>
    <div class="">
        <h2 v-for="table in tables" :key="table">{{ table.id }}</h2>
        <h3 v-for="table in tables" :key="table">{{ table.status }}</h3>
        <li v-for="table in tables">
            
        </li>
    </div>
</template>

<script setup>
const tables = [
    {id:"1", status:"occupied"}
]

</script>

<style scoped>
</style>