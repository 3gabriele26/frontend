<script setup>
  import { RouterLink, RouterView } from 'vue-router'
  import Footer from './components/Footer.vue';
</script>

<template>
  <div class="container_root">
    <header class="logo_container">
      <RouterLink to="/"><img src="./assets/LOGO_ELGA.jpg" alt="ELGA s.r.l. LOGO" class="logo"></RouterLink>
    </header>

    <div>
      <RouterView />
    </div>


    <Footer></Footer>
  </div>
</template>


<style scoped>
  .container_root {
    min-height: 100%;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
  }

  .logo_container {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
  }

  .logo {
    margin: 20px;
    border-radius: 25px;
    height: 100px;
  }

  /* Smartphone fino a 480px */
  @media only screen and (max-width: 767px) {
    .logo_container {
      justify-content: center;
    }

    .logo {
      margin: 0.75rem;
      border-radius: 0.8rem;
      height: 4rem;
    }
  }
</style>
