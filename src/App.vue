<template>
  <nav-component
    @click-home="activeElement = 'home'"
    @click-about="activeElement = 'about'"
    @click-skills="activeElement = 'skills'"
    @click-portfolio="activeElement = 'portfolio'"
    @click-contact="activeElement = 'contact'"
    :active-element="activeElement"
  >
  </nav-component>
  <header-component />
</template>

<script setup>
import { ref } from 'vue'
import NavComponent from './components/NavComponent.vue'
import HeaderComponent from './components/HeaderComponent.vue'

const activeElement = ref('home')
</script>

<style lang="scss"></style>
