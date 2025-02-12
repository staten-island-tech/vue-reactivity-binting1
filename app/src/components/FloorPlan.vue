<template>
    <div class="container">
        <tableCard v-for="table in tables" :key="table.id" :table="table"/>
    </div> 
</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';
import tableCard from "../components/tableCard.vue";

const tables = ref ([
    {id:"1", status:"occupied"},
    {id:"2", status:"unoccupied"},
    {id:"3", status:"unoccupied"},
])

const router = useRouter();

const handleOpenDetail = (id) => {
    router.push({name:'TableDetail', params: {id}});
}

</script>

<style scoped>

</style>