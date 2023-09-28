<template>
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
  <about-component />
</template>

<script setup>
import { ref } from 'vue'
import NavComponent from './components/NavComponent.vue'
import HeaderComponent from './components/HeaderComponent.vue'
import AboutComponent from './components/AboutComponent.vue'
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

<style lang="scss"></style>
