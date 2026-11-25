<script setup lang="ts">
import { ref } from 'vue'
import heroImg from '../assets/hero.png'
import galaxarisLogo from '../assets/logo-galaxaris-square.png'
import networkGif from '../assets/11-07-18-774_512.gif'

const count = ref(0)
</script>

<template>
  <section id="center">
    <div class="hero">
      <img :src="heroImg" class="base" width="170" height="179" alt="" />
    </div>
    <div>
      <h1>RuraLien</h1>
      <p>Welcome to the RuraLien app <span class="beta">- v0.1-Beta</span></p>
    </div>
    <button type="button" class="counter" @click="count++">
      Count is {{ count }}
    </button>
  </section>

  <section id="network">
    <img :src="networkGif" class="network-gif" width="300" height="300" alt="" />
  </section>

  
  <section class="footer">
    <a class="logo-link" href="https://galaxaris.fr/" target="_blank" rel="noopener noreferrer">
      <img :src="galaxarisLogo" class="logo" alt="Galaxaris logo" />
      <div>Galaxaris</div>
    </a>
    <div class="copyright">Copyright © 2024 Galaxaris - All rights reserved.</div>
  </section>

  

  <div class="ticks"></div>
  <section id="spacer"></section>
</template>

<style scoped>
  .network-gif {
    display: block;
    margin: 0 auto;
    background: linear-gradient(#18919F5a, #9198e590);  
    border-radius: 75px;
  }

  .beta {
    font-size: 0.8rem;
    color: #c9c9c9;
    font-style: italic;
  }

  .footer {

    padding: 1rem 0;
  }

  .footer a {
    text-decoration: none;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .footer .copyright {
    text-align: center;
    font-size: 0.8rem;
    color: #c9c9c9;
    font-style: italic;
  }

  .logo-link {
    align-items: center;
    gap: 0.5rem;
    text-align: center;
  }

  .logo-link .logo {
    width: 1.5rem;
    height: 1.5rem;
  }

  .logo-link div, .logo-link div:link, .logo-link div:visited {
    font-size: 1.2rem;
    font-weight: bold;
    color: #fff;
    text-decoration: none;
  }
</style>