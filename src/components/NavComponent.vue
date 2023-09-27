<template>
  <nav>
    <div class="logo">
      <a href="#">KP Portfolio</a>
    </div>
    <div class="menu">
      <a
        href="#"
        id="home"
        @click="$emit('clickHome')"
        :class="activeElement === 'home' ? 'active' : ''"
        >Home
      </a>
      <a
        href="#"
        id="about"
        @click="$emit('clickAbout')"
        :class="activeElement === 'about' ? 'active' : ''"
        >About</a
      >
      <a
        href="#"
        id="skills"
        @click="$emit('clickSkills')"
        :class="activeElement === 'skills' ? 'active' : ''"
        >Skills</a
      >
      <a
        href="#"
        id="portfolio"
        @click="$emit('clickPortfolio')"
        :class="activeElement === 'portfolio' ? 'active' : ''"
        >Portfolio</a
      >
      <a
        href="#"
        id="contact"
        @click="$emit('clickContact')"
        :class="activeElement === 'contact' ? 'active' : ''"
        >Contact</a
      >
    </div>
  </nav>
</template>

<script setup>
import { defineEmits, defineProps } from 'vue'
defineEmits(['clickHome', 'clickAbout', 'clickSkills', 'clickPortfolio', 'clickContact'])
defineProps(['activeElement'])
</script>

<style lang="scss">
nav {
  margin: 0 70px;
  padding: 50px 0;
  display: flex;
  flex-direction: row;
  justify-content: space-between;

  .logo a {
    font-size: 24px;
    color: $secondColor;
  }

  .menu {
    display: flex;
    align-items: center;
    gap: 50px;

    a {
      position: relative;
      color: $textColor;
      font-size: 24px;
      padding-bottom: 10px;

      &::after {
        content: '';
        position: absolute;
        height: 2px;
        width: 0;
        bottom: 0;
        left: 0;
        background-color: $secondColor;
      }

      &:hover::after {
        width: 100%;
      }

      &.active {
        color: $secondColor;

        &::after {
          width: 100%;
        }
      }
    }
  }
}
</style>
