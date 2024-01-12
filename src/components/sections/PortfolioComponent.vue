<template>
  <section id="portfolio" class="portfolio sections">
    <div class="portfolio-container">
      <h2 class="subtitle">My Work</h2>
      <div class="works">
        <div class="work">
          <img
            src="../../assets/portfolio-image-1.png"
            alt="Two laptops used to create the project" />
          <div class="info">
            <h3>PPiSM App</h3>
            <p>Fullstack application for planning assembly processes and systems, made as engineering work.</p>
            <div class="actions">
              <a href="https://ppism-eemo.onrender.com"><i class='bx bx-link-external'></i></a>
              <a href="https://github.com/Kamil678/PPISM" :on-mouseover="selectCode = 'frontend'" :on-mouseout="selectCode = null"><i class='bx bx-code'></i></a>
              <a href="https://github.com/Kamil678/PPISM_Backend" :on-mouseover="selectCode = 'backend'" :on-mouseout="selectCode = null"><i class='bx bx-code'></i></a>
              <div v-if="selectCode === 'frontend'" class="tooltip">Frontend code</div>
              <div v-if="selectCode === 'backend'" class="tooltip">Backend code</div>
            </div>
          </div>
        </div>
        <div class="work">
          <img src="../../assets/portfolio-image-2.png" alt="Phone with applications" />
          <div class="info">
            <h3>Guess Footballer App</h3>
            <p>Application for guessing football players, created in Vue.</p>
            <div class="actions">
              <a href="https://kamil678.github.io/guess-player-app/"><i class='bx bx-link-external'></i></a>
              <a href="https://github.com/Kamil678/guess-player-app"><i class='bx bx-code'></i></a>
            </div>
          </div>
        </div>
        <div class="work">
          <img src="../../assets/portfolio-image-3.png" alt="Programmer creating a project" />
          <div class="info">
            <h3>All Countries App</h3>
            <p>Applications showing all countries obtained by communicating with the API.</p>
            <div class="actions">
              <a href="https://kamil678.github.io/countries-project/"><i class='bx bx-link-external'></i></a>
              <a href="https://github.com/Kamil678/countries-project"><i class='bx bx-code'></i></a>
            </div>
          </div>
        </div>
      </div>
      <a href="https://github.com/Kamil678" class="see-more">See more</a>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const selectCode = ref(null);
</script>

<style lang="scss">
.portfolio {
  margin: 120px 7%;

  .portfolio-container {
    width: 100%;

    .works {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      grid-gap: 40px;
      margin-top: 50px;

      .work {
        border-radius: 10px;
        position: relative;
        overflow: hidden;

        img {
          width: 100%;
          border-radius: 10px;
          display: block;
        }

        &:hover .info {
          height: 100%;
        }

        .info {
          width: 100%;
          height: 0;
          position: absolute;
          left: 0;
          bottom: 0;
          display: flex;
          flex-direction: column;
          align-items: center;
          justify-content: center;
          overflow: hidden;
          background: linear-gradient(180deg, rgba(0, 0, 0, 0.6) 0%, rgba(101, 251, 210, 1) 100%);
          border-radius: 10px;
          padding: 0 40px;
          text-align: center;
          font-size: 14px;
          transition: height 0.4s;

          h3 {
            font-size: 26px;
            font-weight: 500;
            margin-bottom: 20px;
          }

          .actions {
            width: 100%;
            padding: 0 40px;
            margin-top: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0 20px;

            a {
              color: $textColor;
              font-size: 24px;
              line-height: 60px;
            }
          }
        }
      }
    }
  }

  .see-more {
    width: fit-content;
    display: block;
    margin: 50px auto;
    border: 2px solid $secondColor;
    padding: 10px 40px;
    border-radius: 6px;
    color: $textColor;
    transition: background 0.4s;

    &:hover {
      background: $secondColor;
      color: $background;
    }
  }
}
</style>
