<template>
  <nav>
    <div class="menu-wrap">
      <div class="logo">
        <a href="#home"><span>K</span>amil.</a>
      </div>
      <div class="menu">
        <i class="bx bx-x" @click="closeMenu"></i>
        <a
          href="#home"
          @click="$emit('clickHome')"
          :class="activeElement === 'home' ? 'active' : ''">Home
        </a>
        <a
          href="#about"
          @click="$emit('clickAbout')"
          :class="activeElement === 'about' ? 'active' : ''">About</a>
        <!-- <a
          href="#"
          id="skills"
          @click="$emit('clickSkills')"
          :class="activeElement === 'skills' ? 'active' : ''"
          >Skills</a
        > -->
        <a
          href="#portfolio"
          @click="$emit('clickPortfolio')"
          :class="activeElement === 'portfolio' ? 'active' : ''">Portfolio</a>
        <a
          href="#contact"
          @click="$emit('clickContact')"
          :class="activeElement === 'contact' ? 'active' : ''">Contact</a>
      </div>
      <i class="bx bx-menu" @click="showMenu"></i>
    </div>
  </nav>
</template>

<script setup>
import { defineEmits, defineProps } from 'vue'
defineEmits(['clickHome', 'clickAbout', 'clickSkills', 'clickPortfolio', 'clickContact'])
defineProps(['activeElement'])

const showMenu = () => {
  document.querySelector('.menu').classList.add('show')
}

const closeMenu = () => {
  document.querySelector('.menu').classList.remove('show')
}
</script>

<style lang="scss">
nav {
  padding: 15px 0;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 2;
  background: #262626;

  .menu-wrap {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 0 7%;

    .bx-menu,
    .bx-x {
      display: block;
      font-size: 30px;
    }

    .logo a {
      font-size: 36px;
      letter-spacing: 1px;
      font-weight: 500;
      color: $textColor;

      span {
        color: $secondColor;
      }
    }

    .menu {
      display: flex;
      flex-direction: column;
      background-color: $secondColor;
      position: fixed;
      top: 0;
      right: -200px;
      width: 200px;
      height: 100vh;
      padding-top: 50px;
      z-index: 2;
      transition: right 0.4s;

      &.show {
        right: 0;
      }

      a {
        position: relative;
        color: $background;
        font-size: 20px;
        margin: 10px 25px;

        &::after {
          content: '';
          position: absolute;
          height: 2px;
          width: 0;
          bottom: -6px;
          left: 0;
          background-color: $secondColor;
          transition: 0.4s;
        }

        &:hover::after {
          width: 100%;
        }

        &.active {
          color: $textColor;

          &::after {
            width: 0;
          }

          @media only screen and (min-width: $brekpointMedium) {
            color: $secondColor;

            &::after {
              width: 100%;
            }
          }
        }

        @media only screen and (min-width: $brekpointMedium) {
          margin: 0;
          color: $textColor;
        }
      }

      .bx-x {
        position: absolute;
        top: 15px;
        left: 20px;
      }

      @media only screen and (min-width: $brekpointMedium) {
        flex-direction: row;
        align-items: center;
        gap: 40px;
        background-color: transparent;
        position: relative;
        right: 0;
        padding-top: 0;
        height: auto;
        width: auto;
      }
    }

    @media only screen and (min-width: $brekpointMedium) {

      .bx-menu,
      .bx-x {
        display: none;
      }
    }
  }
}
</style>
