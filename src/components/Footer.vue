<script setup>
  import { RouterLink } from 'vue-router'
  import Copyright from './icons/Copyright.vue';

  const copyright_year = new Date().getFullYear()
</script>


<template>
    <div class="footer_primary_container">
        <div class="copyright_credits_container opacity" style="cursor: pointer;">
            <Copyright></Copyright>
            <h6 class="copyright_credits">2024 - {{ copyright_year }}</h6>
        </div>

        <div class="company_container">
            <RouterLink to="/"><h5 class="gold_text hover">ELGA s.r.l.</h5></RouterLink>
            <h6 class="gold_text"> - P.iva 02139780437</h6>
        </div>

        <div class="software_credits_container opacity">
            <h6 class="white_text">Realizzato da:</h6>
            <a href="https://linktr.ee/GSTGRL" class="white_text hover" target="_blank"><h6>GSTGRL</h6></a>
        </div>
    </div>
</template>


<style scoped>

    .opacity {
        opacity: 0.5;
    }
    .opacity:hover {
        opacity: 1;
    }

    .footer_primary_container {
        background-color: #050404;
        border-radius: 10px 10px 0 0;

        height: 30px;

        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }

    .copyright_credits_container {
        display: flex;
        flex-direction: row;
        align-items: center;

        color: white;
        text-align: center;
        
        margin-left: 10px;
    }

    .copyright_credits {
        font-weight: 400;
        text-align: center;
    }

    .company_container {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    .software_credits_container {
        margin-right: 10px;

        display: flex;
        flex-direction: row;
        align-items: center;
    }

    /* Smartphone fino a 480px */
    @media only screen and (max-width: 480px) {
        .copyright_credits_container {
            font-size: 0.5rem;
        }

        .company_container {
            font-size: 0.5rem;
        }

        .software_credits_container {
            font-size: 0.5rem;
        }
    }


    /* Smartphone e piccoli tablet (481px - 767px) */
    @media only screen and (min-width: 481px) and (max-width: 767px) {
        .copyright_credits_container {
            font-size: 0.75rem;
        }

        .company_container {
            font-size: 0.75rem;
        }

        .software_credits_container {
            font-size: 0.75rem;
        }
    }
</style>

