<script setup>
  import { RouterLink } from 'vue-router'
  import "./css/button.css"
  import "./css/container.css"
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
