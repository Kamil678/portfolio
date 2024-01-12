<template>
  <section id="about" class="about sections">
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
          I am a frontend developer and I have been learning the broad frontend for more than 4 years, while I have been working commercially for 2 years. I participated in the creation of projects from
          scratch and maintained existing systems. Every day I try to develop my frontend skills, but also with great enthusiasm I get to know the backend, especially Node.js and PHP.
        </p>
        <div class="tab">
          <p
            class="tab-links"
            :class="activeTab === 'skills' ? 'active-link' : ''"
            @click="activeTab = 'skills'">
            Skills
          </p>
          <p
            class="tab-links"
            :class="activeTab === 'experince' ? 'active-link' : ''"
            @click="activeTab = 'experince'">
            Experience
          </p>
          <p
            class="tab-links"
            :class="activeTab === 'educations' ? 'active-link' : ''"
            @click="activeTab = 'educations'">
            Eductaions
          </p>
        </div>
        <div v-if="activeTab === 'skills'" class="tab-contents">
          <div class="skills-container">
            <div class="skill">
              <img src="../../assets/html.svg" alt="CSS logo" width="50px" />
              <p class="description">HTML</p>
            </div>
            <div class="skill">
              <img src="../../assets/git.svg" alt="CSS logo" width="50px" />
              <p class="description">GIT</p>
            </div>
            <div class="skill">
              <img src="../../assets/css.svg" alt="CSS logo" width="50px" />
              <p class="description">CSS</p>
            </div>
            <div class="skill">
              <img src="../../assets/scss.svg" alt="CSS logo" width="50px" />
              <p class="description">SCSS, SAAS</p>
            </div>
            <div class="skill">
              <img src="../../assets/javascript.svg" alt="CSS logo" width="50px" />
              <p class="description">JavaScript</p>
            </div>
            <div class="skill">
              <img src="../../assets/typescript.svg" alt="CSS logo" width="50px" />
              <p class="description">TypeScript</p>
            </div>
            <div class="skill">
              <img src="../../assets/jquery.svg" alt="CSS logo" width="50px" />
              <p class="description">jQuery</p>
            </div>
            <div class="skill">
              <img src="../../assets/vue.svg" alt="CSS logo" width="50px" />
              <p class="description">Vue</p>
            </div>
            <div class="skill">
              <img src="../../assets/cypress.svg" alt="CSS logo" width="50px" />
              <p class="description">Cypress</p>
            </div>
            <div class="skill">
              <img src="../../assets/react.svg" alt="CSS logo" width="50px" />
              <p class="description basics">Basics React</p>
            </div>
            <div class="skill">
              <img src="../../assets/php.svg" alt="CSS logo" width="50px" />
              <p class="description basics">Basics PHP</p>
            </div>
            <div class="skill">
              <img src="../../assets/nodejs.svg" alt="CSS logo" width="50px" />
              <p class="description basics">Basics Node.js</p>
            </div>
            <div class="skill">
              <img src="../../assets/mongodb.svg" alt="CSS logo" width="50px" />
              <p class="description basics">Basics MongoDB</p>
            </div>
            <div class="skill">
              <img src="../../assets/docker.svg" alt="CSS logo" width="50px" />
              <p class="description basics">Basics Docker</p>
            </div>
          </div>
        </div>
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
import { ref } from 'vue'

const activeTab = ref('skills')
</script>

<style lang="scss">
.about {
  color: #ababab;
  margin: 70px 7% 0 7%;

  .about-container {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    width: 100%;

    .about-col-1 {
      flex-basis: 100%;
      margin-bottom: 30px;

      img {
        background-color: #343434;
        width: 100%;
        border-radius: 15px;
      }

      @media only screen and (min-width: $brekpointMedium) {
        flex-basis: 35%;
        margin-bottom: 0;
      }
    }

    .about-col-2 {
      flex-basis: 100%;
      font-size: 14px;

      .tab {
        display: flex;
        margin: 20px 0 40px 0;

        .tab-links {
          margin-right: 20px;
          font-size: 16px;
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
            transition: 0.4s;

            @media only screen and (min-width: $brekpointMedium) {
              font-size: 18px;
              margin-right: 20px;
            }
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

        .skills-container {
          display: flex;
          align-items: center;
          gap: 20px 20px;
          flex-wrap: wrap;
          //width: 50%;

          .skill {
            background-color: #262626;
            padding: 10px;
            border-radius: 6px;
            transition: transform .4s;
            position: relative;
            min-width: 80px;
            text-align: center;

            &:hover {
              background: $secondColor;
              transform: translateY(-10px);

              .description {
                height: 50%;

                &.basics {
                  height: 60%;
                }
              }
            }

            .description {
              width: 100%;
              display: flex;
              align-items: center;
              justify-content: center;
              height: 0;
              position: absolute;
              left: 0;
              bottom: 0;
              overflow: hidden;
              background: rgba(0, 0, 0, 0.8);
              padding: 0 10px;
              text-align: center;
              font-size: 14px;
              transition: height 0.4s;
              color: $textColor;
            }
          }
        }
      }

      @media only screen and (min-width: $brekpointMedium) {
        flex-basis: 60%;
        font-size: 16px;
      }
    }
  }

  @media only screen and (min-width: $brekpointMedium) {
    margin: 120px 7% 0 7%;
  }
}
</style>
