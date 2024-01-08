<template>
  <header class="header">
    <div class="header-info">
      <p>Frontend Developer</p>
      <h1>Hi, I'm <span>Kamil Pigulak</span><br />From Poland</h1>
    </div>
    <div class="header-image">
      <img src="../../assets/kp-image.png" alt="The photo shows a drawn programmer" />
    </div>
  </header>
</template>

<script setup>
import ButtonComponent from '../shared/ButtonComponent.vue'

function onDownloadCV() {
  const basePath = window.location.origin
  window.open(`${basePath}/src/assets/CV.pdf`, '_blank')
}
</script>

<style lang="scss">
// header {
//   display: grid;
//   grid-template-columns: repeat(1, 1fr);
//   align-items: center;
//   gap: 30px;
//   padding-top: 50px;
//   margin: 0 20px 0 20px;
//   text-align: center;

//   @media (min-width: 975px) {
//     grid-template-columns: repeat(2, 1fr);
//     margin: 0 70px 0 70px;
//   }

//   .header-info {
//     h1 {
//       color: $textColor;
//       font-size: 40px;
//       font-weight: 700;

//       @media (min-width: 975px) {
//         font-size: 56px;
//       }

//       span {
//         -webkit-text-fill-color: transparent;
//         -webkit-text-stroke: 1px #fff;
//       }
//     }

//     p {
//       margin: 30px 0;
//       color: $textColor;
//       font-size: 18px;
//       max-width: 270px;

//       @media (min-width: 975px) {
//         font-size: 16px;
//         max-width: auto;
//       }
//     }
//   }

//   .header-image {
//     img {
//       max-width: 300px;

//       @media (min-width: 480px) {
//         max-width: 400px;
//       }

//       @media (min-width: 768px) {
//         max-width: 600px;
//       }

//       @media (min-width: 1024px) {
//         max-width: 700px;
//       }
//     }
//   }
// }

header.header {
  display: flex;
  align-items: end;
  justify-content: space-between;
  position: relative;

  .header-info {
    align-self: center;
    font-size: 30px;

    h1 {
      font-size: 50px;
      margin-top: 20px;

      span {
        color: $secondColor;
      }
    }
  }

  .header-image {
    img {
      width: 200px;

      @media (min-width: $brekpointMedium) {
        width: 450px;
      }

      @media (min-width: 1280px) {
        width: 550px;
      }
    }
  }
}
</style>
