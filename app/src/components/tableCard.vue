<template>
    <div class="container">
        <h2>{{ table.id }}</h2>
        <h2>{{ table.status }}</h2>
        <button @click="count++"># of reserved spots: {{ count }}</button>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import FloorPlan from '../components/FloorPlan.vue'
defineProps ({
    table: Object,
});

const count = ref(0)

// function occupation() {
//     table.value.status.
// }

</script>

<style scoped>
.container {
    border: 2px solid black;
    padding: 2px;
    margin: 10px;
}
</style>
