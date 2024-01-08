<template>
  <div class="home">
    <nav-component
      @click-home="clickHome"
      @click-about="clickAbout"
      @click-skills="activeElement = 'skills'"
      @click-portfolio="activeElement = 'portfolio'"
      @click-contact="activeElement = 'contact'"
      :active-element="activeElement"
    >
    </nav-component>
    <header-component />
  </div>
  <about-component />
  <portfolio-component />
</template>

<script setup>
import { ref } from 'vue'
import NavComponent from './components/NavComponent.vue'
import HeaderComponent from './components/sections/HeaderComponent.vue'
import AboutComponent from './components/sections/AboutComponent.vue'
import PortfolioComponent from './components/sections/PortfolioComponent.vue'
import { scrollToElement } from './services/helpers'

const activeElement = ref('home')

function clickHome() {
  activeElement.value = 'home'
  scrollToElement('.home')
}

function clickAbout() {
  activeElement.value = 'about'
  scrollToElement('.about')
}
</script>

<style lang="scss">
.home {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100vh;
  margin: 0 7%;
}
</style>
