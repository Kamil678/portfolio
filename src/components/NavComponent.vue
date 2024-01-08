<template>
  <nav>
    <div class="menu-wrap">
      <div class="logo">
        <a href="#"><span>K</span>amil.</a>
      </div>
      <div class="menu">
        <i class="bx bx-x" @click="closeMenu"></i>
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
        <!-- <a
          href="#"
          id="skills"
          @click="$emit('clickSkills')"
          :class="activeElement === 'skills' ? 'active' : ''"
          >Skills</a
        > -->
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
  // position: fixed;
  // top: 0;
  //left: 50%;
  //transform: translateX(-50%);
  width: 100%;
  //background-color: #2b2b2b;

  .menu-wrap {
    display: flex;
    align-items: center;
    justify-content: space-between;

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
      transition: right 0.3s;

      &.show {
        right: 0;
      }

      a {
        position: relative;
        color: $textColor;
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
          transition: 0.3s;
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
