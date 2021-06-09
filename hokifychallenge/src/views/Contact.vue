<template>
    <form class="form" @submit.prevent="validateForm" method="post">  
      <img src="../assets/logo_lovify.svg"/>
      <p v-for="(error,i) in errors" :key="i">{{error}}</p>
    <!-- <span>Homeview</span>   -->
    <label>Vorname: </label>
    <input v-model="vname" placeholder="Vorname">
     <label>Nachname: </label>
    <input v-model="nname" placeholder="Nachname">
     <label>Email: </label>
    <input v-model="email" placeholder="Email">
    <input type="submit" value="submit"/>
  </form>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class Contact extends Vue{

vname = ""
nname = ""
email = ""
errors:Array<string> = []

validateForm(e:any){
  this.errors = [] //reset
  const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
  
  if(this.vname && this.nname && this.email) this.showAlert()

  if(!this.vname) this.errors.push(this.errorString("vname"))  
  if(!this.nname) this.errors.push(this.errorString("nname"))
  if(!this.email) this.errors.push(this.errorString("email"))
  if(this.email && !re.test(this.email)) this.errors.push(this.errorString("emailvalid"))
}

/** 
 * return correct error message 
 **/
errorString(field:string):string{

  let toReturn = ""
  switch(field){
    case "vname": toReturn = "einen Vornamen"
    break
    case "nname": toReturn = "einen Nachnamen"
    break;
    case "email": toReturn = "eine E-Mail Adresse"
    break;
    case "emailvalid": toReturn = "eine gültige E-Mail Adresse"
  }

  return "Bitte geben Sie " + toReturn + " an!"
}

showAlert():void{
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