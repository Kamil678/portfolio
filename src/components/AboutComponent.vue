<template>
  <section class="about">
    <h2>About <span>Me</span></h2>
    <div class="img-container">
      <img src="../assets/kp-image.png" alt="The pictures shows Kamil Pigulak" />
      <span class="spin"></span>
    </div>
    <div class="about-info">
      <h3>Frontend Developer!</h3>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptas repellendus voluptatum
        impedit ut cum excepturi officiis repudiandae, illo expedita qui ea fuga laudantium delectus
        voluptates eos sed ipsam, nesciunt adipisci.
      </p>
    </div>
    <button-component btn-text="Read more" />
  </section>
</template>

<script setup>
import ButtonComponent from './ButtonComponent.vue'
</script>

<style lang="scss">
.about {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 20px 0;
  // height: 100vh;

  h2 {
    color: $textColor;
    font-size: 48px;

    span {
      color: $secondColor;
    }
  }

  .img-container {
    position: relative;
    width: 250px;
    height: 250px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;

    img {
      width: 90%;
      border-radius: 50%;
      border: 2px solid $secondColor;
    }

    .spin {
      width: 100%;
      height: 100%;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) rotate(0);
      border-radius: 50%;
      border-top: 2px solid transparent;
      border-bottom: 2px solid transparent;
      border-left: 2px solid $secondColor;
      border-right: 2px solid $secondColor;
    }
  }

  .about-info {
    text-align: center;
    color: $textColor;

    h3 {
      font-size: 36px;
    }

    p {
      max-width: 1000px;
      font-size: 18px;
    }
  }
}
</style>
