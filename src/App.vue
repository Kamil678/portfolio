<template>
  <nav-component @click-home="onClickHome">
  </nav-component>
</template>

<script setup>
import NavComponent from './components/NavComponent.vue'

function onClickHome() {
  console.log('Click home')
}
</script>

<style lang="scss">
body{
  font-family: 'Poppins', sans-serif;
}
</style>
