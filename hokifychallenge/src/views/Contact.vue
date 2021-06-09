<template>
    <div class="form">  
      <img src="../assets/logo_lovify.svg"/>
    <!-- <span>Homeview</span>   -->
    <label>Vorname: </label>
    <input v-model="vname" placeholder="Vorname">
     <label>Nachname: </label>
    <input v-model="nname" placeholder="Nachname">
     <label>Email: </label>
    <input v-model="email" placeholder="Email">
    <button @click="openWindow">Senden</button>
 
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Contact extends Vue{

vname = ""
nname = ""
email = ""

  openWindow():void{
  alert("Hallo " + this.vname + " " + this.nname + " bei Hokify!");
}
}

</script>

<style lang="scss">
.form{
display: flex;
flex-direction: column;
justify-content: center;
align-items:center;
height: 80vh;
width: 100vw;
img{
  width: 200px;
}
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
    border: 1px solid #cafcfc;
    box-shadow: 1px 2px 8px #96ffff;
    border-radius: 5px;
    cursor: pointer;
     margin: 1rem;   
  }button:hover{
      background: #10b0af;
      transition: 0.5s ease-in-out;
    }
}
</style>