<template>
  <header class="home">
    <div class="header-info">
      <h1>Hi, I am <span>Kamil Pigulak</span>, Frontend Developer</h1>
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Optio illo reprehenderit, natus
        necessitatibus similique culpa voluptatem itaque saepe omnis reiciendis esse earum est
        perspiciatis incidunt blanditiis obcaecati. Facilis, aspernatur ab!
      </p>
      <button-component btn-text="Download CV" @click="onDownloadCV" />
    </div>
    <div class="header-image">
      <img src="../assets/header-img.png" alt="The photo shows a drawn programmer" />
    </div>
  </header>
</template>

<script setup>
import ButtonComponent from './ButtonComponent.vue'

function onDownloadCV() {
  const basePath = window.location.origin
  window.open(`${basePath}/src/assets/CV.pdf`, '_blank')
}
</script>

<style lang="scss">
header {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  align-items: center;
  gap: 30px;
  padding-top: 50px;
  margin: 0 20px 0 20px;
  text-align: center;

  @media (min-width: 975px) {
    grid-template-columns: repeat(2, 1fr);
    margin: 0 70px 0 70px;
  }

  .header-info {
    h1 {
      color: $textColor;
      font-size: 40px;
      font-weight: 700;

      @media (min-width: 975px) {
        font-size: 56px;
      }

      span {
        -webkit-text-fill-color: transparent;
        -webkit-text-stroke: 1px #fff;
      }
    }

    p {
      margin: 30px 0;
      color: $textColor;
      font-size: 18px;
      max-width: 270px;

      @media (min-width: 975px) {
        font-size: 16px;
        max-width: auto;
      }
    }
  }

  .header-image {
    img {
      max-width: 300px;

      @media (min-width: 480px) {
        max-width: 400px;
      }

      @media (min-width: 768px) {
        max-width: 600px;
      }

      @media (min-width: 1024px) {
        max-width: 700px;
      }
    }
  }
}
</style>
