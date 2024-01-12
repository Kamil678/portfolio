<template>
  <header class="header">
    <div class="header-container">
      <div class="header-info">
        <p>Frontend Developer</p>
        <h1>Hi, I'm <span>Kamil Pigulak</span><br />From Poland</h1>
      </div>
      <div class="header-image">
        <img src="../../assets/kp-image.png" alt="The photo shows a drawn programmer" />
      </div>
    </div>
  </header>
</template>

<script setup>
</script>

<style lang="scss">
header.header {
  width: 100%;

  .header-container {
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: space-between;
    position: relative;

    @media (min-width: $brekpointMedium) {
      flex-direction: row;
      align-items: end;
    }

    .header-info {
      align-self: center;
      font-size: 30px;
      margin-bottom: 30px;

      @media (min-width: $brekpointMedium) {
        width: 100%;
        margin-bottom: 0;
      }

      h1 {
        font-size: 30px;
        margin-top: 20px;

        @media (min-width: $brekpointMedium) {
          font-size: 50px;
        }

        span {
          color: $secondColor;
        }
      }
    }

    .header-image {
      img {
        display: none;

        @media (min-width: $brekpointMedium) {
          display: block;
          width: 400px;
        }


        @media (min-width: $brekpointLarge) {
          width: 450px;
        }

        @media (min-width: 1280px) {
          width: 550px;
        }
      }
    }
  }
}
</style>
