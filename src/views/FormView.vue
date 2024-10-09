<script setup>
    import {setCookie, getCookie} from "../javascipt/cookies"
    import { RouterLink } from 'vue-router'
    import "./css/container.css"
    
</script>

<template>
    <div class="form_view" @submit.prevent="submitForm">
        <form class="form_container container" id="questionario">
            <input type="text" placeholder="NOME" required v-model="formData.name">
            <input type="text" placeholder="COGNOME"  required v-model="formData.surname">
            <input type="email" placeholder="EMAIL" required v-model="formData.email">
            <input type="tel" placeholder="TELEFONO" required v-model="formData.number">
            <input type="text" placeholder="RUOLO AZIENDALE" required v-model="formData.company_role">
            <textarea placeholder="SCRIVI QUALCOSA SU DI TE..." maxlength="300" v-model="formData.message"></textarea>

            <div class="privacy_policy">
                <input type="checkbox"  style="box-shadow: none;" required disabled id="privacy_policy_checkbox">
                <h6 class="smaller_text"><a style="color: #c2b590;" class="hover" @click="privacyPolicyViewed">Privacy Policy</a></h6>
            </div>

            <button class="button" type="submit" form="questionario" value="INVIA" >
                <h2 class="button_text">INVIA</h2>
            </button>
        </form>
    </div>
</template>


<script>
    import axios from 'axios';

    export default {
        mounted() {
            if(getCookie("Privacy Policy Read")) {
                document.querySelector("#privacy_policy_checkbox").disabled = false
            }
        },
        data() {
            return {
                formData: {
                    name: '',
                    surname: '',
                    email: '',
                    number: '',
                    company_role: '',
                    message: ''
                }
            };
        },
        methods: {
            async submitForm() {
                try {
                    this.$router.replace('/thanks');
                    //const response = await axios.post('http://127.0.0.1:5000/send-email', this.formData)
                    const response = await axios.post('https://elga-af9efdb3b7ea.herokuapp.com/send-email', this.formData) //For debug 
                    console.log(response)
                    //alert('Email inviata con successo!');
                } catch (error) {
                    console.error('Errore durante l\'invio dell\'email:', error);
                    alert('Errore durante l\'invio.');
                }
            },
            privacyPolicyViewed: function() {
                setCookie("Privacy Policy Read", true, 1)
                document.querySelector("#privacy_policy_checkbox").disabled = false
            }
        }
    }
</script>


<style>
    input {
        height: 28px;
    }

    textarea {
        resize: none;
        min-height: 100px;
        max-height: 150px;
    }

    .form_view {
        margin: auto
    }

    .form_container {
        display: flex;
        flex-direction: column;

        padding: 15px;
        margin: 1.2rem auto;
        max-width: 31rem;
    }

    .privacy_policy {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    /* Smartphone fino a 480px */
    @media only screen and (max-width: 767px) {
        input {
            height: 1.2rem;
            font-size: 0.75rem;
            border-radius: 0.4rem;
        }

        .form_container {
            max-width: 20rem;
        }

        ::placeholder {
            font-size: 0.4rem;
        }      

        .smaller_text {
            font-size: 0.5rem;
        }
    }  
    
</style>
  