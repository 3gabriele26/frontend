<script setup>
  import { RouterLink, RouterView } from 'vue-router'
  import "./assets/button.css"
  import Footer from './components/Footer.vue';
</script>

<template>
  <div class="container_root">
    <header>
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

  .logo {
    margin: 20px;
    border-radius: 25px;
    height: 100px;
  }

  @media (min-width: 1024px) {
    header {
      display: flex;
      place-items: center;
      padding-right: calc(var(--section-gap) / 2);
    }

    header .wrapper {
      display: flex;
      place-items: flex-start;
      flex-wrap: wrap;
    }

    nav {
      text-align: left;
      margin-left: -1rem;
      font-size: 1rem;

      padding: 1rem 0;
      margin-top: 1rem;
    }
  }
</style>
