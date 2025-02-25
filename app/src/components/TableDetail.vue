<template>
    <div class="container">
      <h1>Reservation for Table <strong>{{ table.id }}</strong> </h1>
      <form action="submit" @submit.prevent="prevent">
        <label for="name">Reserver Name: </label>
        <input type="text" v-model='reserve.name'/>
        <br>
        <label for="guests">Number of Guest(s): </label>
        <input type="number" v-model='reserve.guests'/>
        <br>
        <label for="time">Time of Reservation: </label>
        <input type="time" v-model='reserve.time'/>
        <br>
        <button type="submit">submit</button>
      </form>
      <div v-if="messages.length > 0" class="message-list">
        <h3>Messages:</h3>
        <ul>
          <li v-for="(message, index) in messages" :key="index">{{ message }}</li>
        </ul>
      </div>
    
    </div>
    
</template> 

<script setup>
import { reactive, ref } from 'vue'
import {tableData} from '../tables.js'
const reserve = reactive({name:'', guests:'', time:''});
const messages = ref ([]);


const props = defineProps ({
    table: Object,
});

const emit = defineEmits(['submit']);

function prevent() {
  if (reserve.name && reserve.guests && reserve.time) {
    emit('submit', reserve, props.table.id); // Emit reserve and table ID
    const newMessage = ` ${reserve.name} reserved for ${reserve.guests} guests at ${reserve.time}.`;
    messages.value.push(newMessage);
    reserve.name = '';
    reserve.guests = '';
    reserve.time = '';
  } else {
    alert(`Please fill in all fields.`);
  }
}

</script>
  
<style scoped>
.container {
  background-color: #fff;
  padding: 20px;
  border-radius: 8px;
  border: 1px solid #ccc;
  max-width: 400px;
  margin: 0 auto;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

form {
  display: flex;
  flex-direction: column;
}

form label {
  margin-top: 10px;
  font-size: 14px;
  color: #495057;
}

form input {
  padding: 10px;
  margin-top: 5px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 14px;
  color: #495057;
}

form input:focus {
  border-color: #02804b;
  outline: none;
}

form button {
  padding: 12px;
  background-color: #00bd7e;
  color: white;
  border-radius: 5px;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease;
}
</style>