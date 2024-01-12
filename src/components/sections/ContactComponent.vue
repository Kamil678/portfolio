<template>
  <section id="contact" class="contact sections">
    <div class="contact-container">
      <div class="contact-info">
        <h2 class="subtitle">Contact Me</h2>
        <div class="email">
          <i class='bx bx-envelope'></i>
          <p>kamilpigulak@gmail.com</p>
        </div>
        <div class="phone">
          <i class='bx bx-phone'></i>
          <p>518144228</p>
        </div>
        <div class="socials">
          <a href="https://www.facebook.com/kamil.pigulak/"><i class='bx bxl-facebook-circle'></i></a>
          <a href="https://www.linkedin.com/in/kamil-pigulak/"><i class='bx bxl-linkedin-square'></i></a>
          <a href="https://github.com/Kamil678"><i class='bx bxl-github'></i></a>
        </div>
        <button-component btn-text="Download CV" @click="onDownloadCV" />
      </div>
      <div class="contact-form">
        <form action="https://formsubmit.co/kamilpigulak@gmail.com" method="POST">
          <input type="text" name="name" placeholder="Your name" required>
          <input type="email" name="email" placeholder="Your email" required>
          <textarea name="message" rows="6" placeholder="Your message"></textarea>
          <input type="hidden" name="_next" value="http://localhost:5173#contact?sendEmail=true">
          <input type="hidden" name="_captcha" value="false">
          <p v-if="isSendEmail" class="success-message">Message was sent</p>
          <button type="submit" class="basic-btn btn-with-background">Submit</button>
        </form>
      </div>
    </div>
  </section>
  <footer-component />
</template>

<script setup>
import FooterComponent from './FooterComponent.vue';
import ButtonComponent from '../shared/ButtonComponent.vue';

defineProps(['isSendEmail'])

function onDownloadCV() {
  const basePath = window.location.origin
  window.open(`${basePath}/src/assets/CV.pdf`, '_blank')
}
</script>

<style lang="scss">
.contact {
  margin: 50px 7% 0 7%;

  .contact-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 100%;

    .contact-info {
      flex-basis: 100%;
      margin-bottom: 30px;

      .email,
      .phone {
        margin-top: 20px;
        display: flex;
        align-items: center;

        i {
          color: $secondColor;
          margin-right: 10px;
          font-size: 25px;
        }
      }

      .socials {
        margin: 30px 0;

        a {
          font-size: 30px;
          margin-right: 10px;
          color: #ababab;
          display: inline-block;
          transition: transform 0.4s;

          &:hover {
            color: $secondColor;
            transform: translateY(-5px);
          }
        }
      }

      @media only screen and (min-width: $brekpointMedium) {
        flex-basis: 35%;
        margin-bottom: 0;
      }
    }

    .contact-form {
      flex-basis: 100%;

      form {
        width: 100%;

        input,
        textarea {
          width: 100%;
          border: 0;
          outline: none;
          background: #262626;
          color: $textColor;
          font-size: 18px;
          padding: 15px;
          margin: 15px 0;
          border-radius: 6px;
        }

        button {
          padding: 10px 60px;
          font-size: 18px;
          margin-top: 20px;
        }

        .success-message {
          color: #61b752;
        }
      }

      @media only screen and (min-width: $brekpointMedium) {
        flex-basis: 60%;
      }
    }

    @media only screen and (min-width: $brekpointMedium) {
      flex-direction: row;
    }
  }
}
</style>
