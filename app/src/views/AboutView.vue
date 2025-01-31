<script setup>
import FloorPlan from '../components/FloorPlan.vue'
</script>

<template>
  <div class="about">
    <FloorPlan/>
  </div>
  
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
