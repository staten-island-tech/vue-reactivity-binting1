<template>
    <div class="container">
        <h2>{{ table.id }}</h2>
        <h2>{{ table.status }}</h2>
        <button @click="count++" @submit.prevent="count"># of reserved spots: {{ count }}</button>
        <br><button @click="openDetailPage">click to reserve</button>
    </div>
</template>

<script setup>
import { ref } from 'vue'
defineProps ({
    table: Object,
    id: Number, 
    status: String,
    
});

const count = ref(0)

// function event () {
//     spots.append()
// }

</script>

<style scoped>
.container {
    border: 2px solid black;
    padding: 2px;
    margin: 10px;
}
</style>
