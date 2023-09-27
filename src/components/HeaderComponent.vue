<template>
  <header>
    <div class="header-info">
      <h1>Hi, I am <span>Kamil Pigulak</span>, Frontend Developer</h1>
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Optio illo reprehenderit, natus
        necessitatibus similique culpa voluptatem itaque saepe omnis reiciendis esse earum est
        perspiciatis incidunt blanditiis obcaecati. Facilis, aspernatur ab!
      </p>
      <button-component btn-text="Get started" />
    </div>
    <div class="header-image">
      <img src="../assets/header-img.png" alt="The photo shows a drawn programmer" />
    </div>
  </header>
</template>

<script setup>
import ButtonComponent from './ButtonComponent.vue'
</script>

<style lang="scss">
header {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  align-items: center;
  gap: 30px;
  margin: 50px 70px 0 70px;

  @media (max-width: 975px) {
    grid-template-columns: repeat(1, 1fr);
  }

  .header-info {
    h1 {
      color: $textColor;
      font-size: 45px;
      font-weight: 700;

      span {
        -webkit-text-fill-color: transparent;
        -webkit-text-stroke: 1px #fff;
      }
    }

    p {
      margin: 30px 0;
      color: $textColor;
      font-size: 18px;
    }
  }

  .header-image {
    img {
      max-width: 600px;
    }
  }
}
</style>
