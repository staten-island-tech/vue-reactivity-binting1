<template>
  <div>
    <form action="submit" @submit.prevent="reserve">
      <label for="table">table number</label>
      <input type="text" v-model='reserve.username'/>
      <br>
      <label for="guests">amount of guests</label>
      <input type="text" v-model='reserve.password'/>
      <br>
      <button >submit</button>
    </form>
    <h2 v-if="loggedIn">hello</h2>
    <h2 v-else>please login</h2> 
  </div>
</template> 

<script setup>
  import { reactive } from 'vue' //ref is for individual data, reactive is for arrays and objects
  const reserve = reactive({table:'', guests:''}) //should be together to define one user
  function vy(reserve){
    console.log(reserve)
  }
  vy(reserve);
  const loggedIn = false; 

  //to render the data, use v-(word) in the template 
  //and click@ to add new data to a data object or array (here, the object is called user)

</script>

<style scoped>

</style>