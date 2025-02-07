<template>
    <div class="container">
        <h2>{{ table.id }}</h2>
        <h2>{{ table.status }}</h2>
        <button @click="count++"># of reserved spots: {{ count }}</button>
        <br><button @click="sidebar()">click to reserve</button>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import spots from '../components/spotsReserved.vue'
import Reservations from '../components/Reservations.vue'
defineProps ({
    table: Object,
});

const count = ref(0)

function sidebar () {
    spots.append(reserve)
}

</script>

<style scoped>
.container {
    border: 2px solid black;
    padding: 2px;
    margin: 10px;
}
</style>
