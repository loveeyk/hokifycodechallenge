<template>
    <div class="form">  
    <!-- <span>Homeview</span>   -->
    <label>Vorname: </label>
    <input v-model="text" placeholder="Vorname">
     <label>Nachname: </label>
    <input v-model="text" placeholder="Nachname">
     <label>Email: </label>
    <input v-model="email" placeholder="Email">
    <button @click="openWindow">Senden</button>
 
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Contact extends Vue{

openWindow(){
  alert("Hallo Loveleen Karir bei Hokify")

  return 1
}
}

</script>

<style lang="scss">
.form{
display: flex;
flex-direction: column;
justify-content: center;
align-items:center;
height: 100vh;

label{
  padding-top: 1rem;
}
input{
  padding: 0.5rem;
  width: 300px;
}
  button{
    background: #027f7e;
    color: white;
    padding: 1rem;
    border-radius: 5px;
    cursor: pointer;
     border: 1px solid transparent;
    
  }button:hover{
      background: #10b0af;
    }
}
</style>