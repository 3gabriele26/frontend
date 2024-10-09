<script setup>
  import { RouterLink } from 'vue-router'
  import "./css/button.css"
  import "./css/container.css"
</script>

<template>
  <div class="container">
    <div class="quote_container">
      <h3 class="quote">Grazie per averci contattati !</h3>
    </div>

    <RouterLink to="/" class="button_div">
      <div class="button">
        <h2 class="button_text">TORNA ALLA HOME</h2>
      </div>
    </RouterLink>
    
  </div>  
</template>