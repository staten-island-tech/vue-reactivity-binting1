<template>
  <div>
    <form action="submit" @submit.prevent="login">
      <label for="username">username</label>
      <input type="text" v-model='user.username'/>
      <br>
      <label for="password">password</label>
      <input type="text" v-model='user.password'/>
      <br><button>submit</button>
    </form>
    <h2 v-if="loggedIn">hello</h2>
    <h2 v-else>please login</h2> 
  </div>
</template> 

<script setup>
  import { reactive } from 'vue' //ref is for individual data, reactive is for arrays and objects
  const user = reactive({username:'', password:''}) //should be together to define one user
  function login(user){
    console.log(user)
  }
  login(user);
  const loggedIn = false; 

  //to render the data, use v-(word) in the template 
  //and click@ to add new data to a data object or array (here, the object is called user)

</script>

<style scoped>

</style>