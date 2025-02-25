<template>
    <div class="container">
        <h2>Table {{ table.id }}: {{ table.occupied }}</h2>
        <button># of reserved spots: {{ count }}</button>
        <br><button @click="openPage">click to reserve</button>
        <TableDetail @submit="submitted" :table="table" v-show="show"></TableDetail>
        <div v-if="message" class="message">
            <p>{{ message }}</p>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import { tableData} from '../tables.js'
import TableDetail from './TableDetail.vue'
defineProps ({
    table: Object,
    id: Number, 
    occupied: Boolean,
});

const count = ref(0)
const show = ref(false)

const openPage = () => {
    show.value = true;
}

function submitted(reserve, id) {
  const table = tableData.tables.find((table) => table.id === id);
  if (table) {
    table.occupied = true;
    count.value++
}   
}
</script>

<style scoped>
.container {
    border: 2px solid black;
    padding: 15px;
    margin: 20px;
    background-color: #f8f9fa;
    border-radius: 8px;
    box-shadow: 0 2px 4px; 
    max-width: 400px;
    margin-left: auto; 
    margin-right: auto;
}

.container h2 {
    font-size: 18px;
    color: #343a40;
    text-align: center;
}

h2 {
    color: green; 
    font-weight: bold;
}

button {
    margin: 10px 0;
    padding: 10px 20px;
    background-color: #00bd7e;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
    font-size: 16px;
}

button:hover {
    background-color: #029766;
}

@media (max-width:1500px) {
    .container {
        width: 100%;
        padding: 10px;
    }

    button {
        width: 100%;
    }
}
</style>
