<template>
    <div class="container">
        <h2>{{ table.id }}</h2>
        <h2>{{ table.status }}</h2>
        <button>register for spot</button>
    </div>
</template>

<script setup>
defineProps ({
    table: Object,
});
</script>

<style scoped>
.container {
    border: 2px solid black;
    padding: 2px;
    margin: 10px;
}
</style>
