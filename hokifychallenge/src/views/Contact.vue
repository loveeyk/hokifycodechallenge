<template>
<form class="form" @submit.prevent="validateForm" method="post">
    <img src="../assets/logo_lovify.svg" />
    <div class="form_wrapper">
        <div class="labelTag">
            <label for="">*Vorname: </label>
            <label for="">*Nachname: </label>
            <label for="">*Email: </label></div>
        <div class="inputWrapper"> <input type="text" v-model="vname">
            <input type="text" v-model="nname">
            <input type="text" v-model="email">
            <input type="submit" value="Absenden" />
        </div>
    </div>
</form>
<div class="err" v-if="errors.length > 0">
    <p class="error" v-for="(error,i) in errors" :key="i">{{error}}</p>
</div>
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

.err {
    border: 1px solid $color_alert;
    max-width: 500px;
    margin: 0 auto;
    border-radius: 5px;
}

.error {
    font-size: 0.8rem;
    color: $color_alert;
    margin: 0.5rem;
    text-align: center;

}

.form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding-top: 0.5rem;
    height: 100%;
    .form_wrapper {
        position: relative;
        .labelTag {
            display: flex;
            flex-direction: column;
            position: absolute;
            top: -20px;
            label {
                background: $accent_colorLight;
                margin: 1.6rem;
                font-size: smaller;
            }
        }
        .inputWrapper {
            display: flex;
            flex-direction: column;

            input {
                &[type='text'] {
                    padding: 0.5rem;
                    width: 300px;
                    border-radius: 5px;
                    border-width: 1px;
                    margin: 1rem;
                }
                &[type='submit'] {
                    background: $color_blue;
                    color: $accent_colorLight;
                    padding: 0.5rem;
                    border: 1px solid $accent_colorLight;
                    border-radius: 5px;
                    cursor: pointer;
                    margin: 1rem;
                    &:hover {
                        background: #6dadf1c9;
                        transition: 0.5s ease-in-out;
                    }
                }
            }
        }
    }
}
</style>
