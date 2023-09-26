<template>
  <nav>
    <div class="logo">
      <a href="#">KP Portfolio</a>
    </div>
    <div class="menu">
      <a href="#" id="home" @click="$emit('clickHome')">Home</a>
      <a href="#" id="about" @click="$emit('clickAbout')">About</a>
      <a href="#" id="skills" @click="$emit('clickSkills')">Skills</a>
      <a href="#" id="portfolio" @click="$emit('clickPortfolio')">Portfolio</a>
      <a href="#" id="contact" @click="$emit('clickContact')">Contact</a>
    </div>
  </nav>
</template>

<script setup>
import { defineEmits } from 'vue'
defineEmits(['clickHome', 'clickAbout', 'clickSkills', 'clickPortfolio', 'clickContact'])
</script>

<style lang="scss">
nav {
  max-width: 1200px;
  margin: 0 auto;
  padding: 30px 0;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  background-color: $color;
}
</style>
