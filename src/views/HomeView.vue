<script setup>
  import { RouterLink } from 'vue-router'
  import "../assets/button.css"
</script>

<template>
  <div class="container">
    <div class="quote_container">
      <h3 class="quote">“Soltanto una cosa rende impossibile un sogno:<br>la paura di fallire”</h3>
    </div>

    <RouterLink to="/form" class="button_div">
      <div class="button">
        <h2 class="button_text">CONTATTACI</h2>
      </div>
    </RouterLink>
    
  </div>  
</template>



<style scoped>
  .container {
    background: rgba(255, 255, 255, 0.6);
    border-radius: 15px;
    box-shadow: 0px 0px 5px 0px #050404;

    margin: 0 auto;
    max-width: 600px;
    padding: 60px;
  }

  .quote_container {
    text-align: center;
  }

  .quote {
    font-weight: 700;
    color: #050404;
  }

  .button_div {
    text-align: center;
  }

  .button {
    margin-top: 30px;
    flex-grow: 100;
  }

</style>
