<script setup>
import { RouterLink, RouterView } from 'vue-router';
import TableCard from './components/Table.vue';
import HelloWorld from './components/HelloWorld.vue';
import { tableData } from './tables.js';
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->
      <div class="wrapper">
        <img alt="herbs" src="@/assets/herbs.jpg" width="500" height="300"/>
        <HelloWorld msg="Forestry Eats"/>
      </div>
      <div class="cards">
        <TableCard v-for="table in tableData.tables" :key="table.id" :table="table" />
      </div>
  </header>
</template>

<style scoped>
.header {
  background-color: #007BFF;
  color: white;
  display: flex;
  justify-content: center;
  padding: 15px;
  text-align: center;
  font-size: 24px;
  font-weight: bold;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.cards {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  padding: 20px;
  gap: 20px;
  margin-top: 20px;
}

@media (min-width: 1024px) {
  header {
    display: grid;
    place-items: center;
    padding: 20px;
  }

} 

img {
  max-width: 100%;
  max-height: 100%;
}
</style>
