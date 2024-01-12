<template>
  <div id="home" class="home sections">
    <nav-component
      @click-home=" activeElement = 'home'"
      @click-about="activeElement = 'about'"
      @click-portfolio="activeElement = 'portfolio'"
      @click-contact="activeElement = 'contact'"
      :active-element="activeElement">
    </nav-component>
    <header-component />
  </div>
  <about-component />
  <portfolio-component />
  <contact-component :is-send-email="search" />
</template>

<script setup>
import { ref, onMounted } from 'vue'
import NavComponent from './components/NavComponent.vue'
import HeaderComponent from './components/sections/HeaderComponent.vue'
import AboutComponent from './components/sections/AboutComponent.vue'
import PortfolioComponent from './components/sections/PortfolioComponent.vue'
import ContactComponent from './components/sections/ContactComponent.vue'
import { scrollToElement } from './services/helpers'

const activeElement = ref('home')

const search = ref(null);
onMounted(() => {
  window.onscroll = () => {
    const sections = document.querySelectorAll('.sections');

    sections.forEach(section => {
      const top = window.scrollY;
      const height = section.offsetHeight;
      const offset = section.offsetTop - 200;
      const id = section.getAttribute('id')

      if (top >= offset && top < offset + height) {
        activeElement.value = section.getAttribute('id')
      }
    })
  }

  search.value = window.location.href.includes("?") ? true : false
  if (search.value) {
    scrollToElement("#contact")
    setTimeout(() => {
      search.value = false
    }, 10000)
  }
})

</script>

<style lang="scss">
.home {
  display: flex;
  flex-direction: column;
  justify-content: start;
  margin: 0 7%;
  margin-top: 130px;

  @media (min-width: $brekpointMedium) {
    justify-content: end;
    margin-top: 0;
    height: 100vh;
  }
}
</style>
