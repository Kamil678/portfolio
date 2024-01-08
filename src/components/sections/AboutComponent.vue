<template>
  <section class="about">
    <!-- <h2>About <span>Me</span></h2>
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
    <button-component btn-text="Read more" /> -->
    <div class="about-container">
      <div class="about-col-1">
        <img src="../../assets/kp-image.png" alt="The pictures shows Kamil Pigulak" />
      </div>
      <div class="about-col-2">
        <h2 class="subtitle">About <span>Me</span></h2>
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit quis sequi inventore
          quaerat quod incidunt, voluptatibus consequuntur amet odio perferendis provident! Adipisci
          suscipit maxime sequi necessitatibus, quaerat iusto doloribus velit!
        </p>
        <div class="tab">
          <p
            class="tab-links"
            :class="activeTab === 'skills' ? 'active-link' : ''"
            @click="activeTab = 'skills'"
          >
            Skills
          </p>
          <p
            class="tab-links"
            :class="activeTab === 'experince' ? 'active-link' : ''"
            @click="activeTab = 'experince'"
          >
            Experience
          </p>
          <p
            class="tab-links"
            :class="activeTab === 'educations' ? 'active-link' : ''"
            @click="activeTab = 'educations'"
          >
            Eductaions
          </p>
        </div>
        <!-- <div class="tab-contents">
          <div>
            <img src="../../assets/css.svg" alt="CSS logo" />
          </div>
        </div> -->
        <div v-if="activeTab === 'experince'" class="tab-contents">
          <ul>
            <li><span>05.2022 - Current</span><br />Frontend Developer at Mediaflex</li>
          </ul>
        </div>
        <div v-if="activeTab === 'educations'" class="tab-contents">
          <ul>
            <li><span>2020-2024</span><br />BSc from automation and robotics</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import ButtonComponent from '../shared/ButtonComponent.vue'
import { ref } from 'vue'

const activeTab = ref('skills')
</script>

<style lang="scss">
// .about {
//   display: flex;
//   flex-direction: column;
//   align-items: center;
//   justify-content: center;
//   gap: 20px 0;
//   // height: 100vh;

//   h2 {
//     color: $textColor;
//     font-size: 48px;

//     span {
//       color: $secondColor;
//     }
//   }

//   .img-container {
//     position: relative;
//     width: 250px;
//     height: 250px;
//     border-radius: 50%;
//     display: flex;
//     align-items: center;
//     justify-content: center;

//     img {
//       width: 90%;
//       border-radius: 50%;
//       border: 2px solid $secondColor;
//     }

//     .spin {
//       width: 100%;
//       height: 100%;
//       position: absolute;
//       top: 50%;
//       left: 50%;
//       transform: translate(-50%, -50%) rotate(0);
//       border-radius: 50%;
//       border-top: 2px solid transparent;
//       border-bottom: 2px solid transparent;
//       border-left: 2px solid $secondColor;
//       border-right: 2px solid $secondColor;
//     }
//   }

//   .about-info {
//     text-align: center;
//     color: $textColor;

//     h3 {
//       font-size: 36px;
//     }

//     p {
//       max-width: 1000px;
//       font-size: 18px;
//     }
//   }
// }
.about {
  padding: 80px 0;
  color: #ababab;
  margin: 0 7%;

  .about-container {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;

    .about-col-1 {
      flex-basis: 35%;

      img {
        background-color: #343434;
        width: 100%;
        border-radius: 15px;
      }
    }

    .about-col-2 {
      flex-basis: 60%;

      .tab {
        display: flex;
        margin: 20px 0 40px 0;

        .tab-links {
          margin-right: 50px;
          font-size: 18px;
          font-weight: 500;
          cursor: pointer;
          position: relative;

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

          &.active-link {
            color: $secondColor;

            &::after {
              width: 100%;
            }
          }
        }
      }

      .tab-contents {
        ul {
          li {
            list-style: none;
            margin: 10px 0;

            span {
              color: $secondColor;
              font-size: 14px;
            }
          }
        }
      }
    }
  }
}
</style>
