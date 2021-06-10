<template>
<form class="form" @submit.prevent="validateForm" method="post">
    <img src="../assets/logo_lovify.svg" />
    <p class="error" v-for="(error,i) in errors" :key="i">{{error}}</p>
    <label for="">Vorname: </label>
    <input type="text" v-model="vname" placeholder="Vorname">
    <label for="">Nachname: </label>
    <input type="text" v-model="nname" placeholder="Nachname">
    <label for="">Email: </label>
    <input type="text" v-model="email" placeholder="Email">
    <input type="submit" value="Absenden" />
</form>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";
import Swal from 'sweetalert2'


export default class Contact extends Vue {

    vname = ""
    nname = ""
    email = ""
    errors: Array < string > = []
  swal: any;
  $swal: any;
/**
 * check form input validation
 */
    validateForm(e: any) {
        this.errors = [] //reset
        const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;

        if (this.vname && this.nname && this.email && re.test(this.email)) this.showAlert()
        if (!this.vname) this.errors.push(this.errorString("vname"))
        if (!this.nname) this.errors.push(this.errorString("nname"))
        if (!this.email) this.errors.push(this.errorString("email"))
        if (this.email && !re.test(this.email)) this.errors.push(this.errorString("emailvalid"))
    }
    /** 
     * return correct error message 
     **/
    errorString(field: string): string {
        let toReturn = ""
        switch (field) {
            case "vname":
                toReturn = "einen Vornamen"
                break
            case "nname":
                toReturn = "einen Nachnamen"
                break;
            case "email":
                toReturn = "eine E-Mail Adresse"
                break;
            case "emailvalid":
                toReturn = "eine gültige E-Mail Adresse"
        }
        return "Bitte geben Sie " + toReturn + " an!"
    }
    showAlert(): void {
       Swal.fire({
          title: "Willkommen!",
          text: "Hallo " + this.vname + " " + this.nname + " bei Hokify!", 
          confirmButtonColor: '#027f7e', 
          background: '#cafcfcd1'
         });
    }
}
</script>

<style lang="scss">
@import 'src/assets/colors.scss';
img {
        width: 135px;
    }
.form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding-top: 0.5rem;
    height: 100%;
    
    .error {
        font-size: 0.8rem;
        color: $accent_colorDark;
        margin: 0.5rem;
    }
    
    label {
        padding-top: 0.5rem;
    }
    input {
        &[type='text'] {
            padding: 0.5rem;
            width: 300px;
        }
        &[type='submit'] {
            background: $color_dark;
            color: $accent_colorLight;
            padding: 0.5rem;
            border: 1px solid #cafcfc;
            box-shadow: 1px 2px 8px #96ffff;
            border-radius: 5px;
            cursor: pointer;
            margin: 1rem;
            &:hover {
                background: $color;
                transition: 0.5s ease-in-out;
            }
        }
    }
}
</style>
