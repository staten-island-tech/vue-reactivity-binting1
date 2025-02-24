<template>
    <div class="container">
        <tableCard @click="openPage(table)" v-for="table in tables" :key="table.id" :table="table">reserve</tableCard>
    </div> 
</template>

<script setup>
import { ref } from 'vue';
import tableCard from "../components/tableCard.vue";

const tables = ref ([
    {id:"1", status:"occupied"},
    {id:"2", status:"unoccupied"},
    {id:"3", status:"unoccupied"},
])

const openPage = (table) => {
    list.cart.push(table)
}


</script>

<style scoped>

</style>