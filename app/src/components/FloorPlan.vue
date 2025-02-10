<template>
    <div class="container">
        <tableCard v-for="table in tables" :key="table.id" :table="table"/>
    </div> 
</template>

<script setup>
import tableCard from "../components/tableCard.vue"
const tables =  [
    {id:"1", status:"occupied"},
    {id:"2", status:"unoccupied"},
    {id:"3", status:"unoccupied"},
]



</script>

<style scoped>

</style>