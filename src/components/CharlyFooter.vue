<template>
  <footer class="charly-footer container">
    <div class="charly-footer__map-container">
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2513.8470072822574!2d2.1947512156350513!3d50.94504237954659!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47dc5ef733edb497%3A0x9c3df032d42f1ad2!2s26%20Rue%20Paul%20Machy%2C%2059630%20Bourbourg!5e0!3m2!1sfr!2sfr!4v1669729618896!5m2!1sfr!2sfr"
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
      ></iframe>
    </div>

    <div class="charly-footer__link-top-map">
      <a href="https://goo.gl/maps/LtAaLrWJzK26djqPA" target="blank"
        ><i class="fa-solid fa-location-dot" /> 26 rue Paul Machy, 59630,
        Bourbourg</a
      >
    </div>

    <ul class="charly-footer__shop-images">
      <li>
        <img
          class="charly-footer__img"
          src="../assets/studio/studio.jpg"
          alt="Devanture du studio"
        />
      </li>
      <li>
        <img
          class="charly-footer__img"
          src="../assets/studio/frontDesk.jpg"
          alt="Accueil"
        />
      </li>
      <li>
        <img src="../assets/studio/shootingSpace.jpg" alt="Espace shooting" />
      </li>
    </ul>

    <div class="charly-footer__contacts" id="contacts">
      <h2 class="charly-footer__contacts__title">Contacts</h2>

      <ul class="charly-footer__contacts__list">
        <li>
          <a
            href="https://www.instagram.com/studio_charly_photo/"
            target="blank"
            ><i class="charly-icon fa-brands fa-instagram fa-2xl"></i
            >@studio_charly_photo</a
          >
        </li>
        <li>
          <a href="https://www.facebook.com/studiophotobourbourg" target="blank"
            ><i class="charly-icon fa-brands fa-facebook-f fa-xl"></i>Studio
            Charly</a
          >
        </li>
        <li>
          <a
            href="https://www.linkedin.com/in/charly-photographe-b40603254/"
            target="blank"
            ><i class="charly-icon fa-brands fa-linkedin fa-2xl"></i>Charly
            Photographe</a
          >
        </li>
        <li>
          <a href="mailto:studio.charly.bourgourg@gmail.com"
            ><i class="charly-icon fa-regular fa-envelope fa-2xl"></i
            >studio.charly.bourgourg@gmail.com</a
          >
        </li>
        <li>
          <a href="tel:06-82-53-68-07"
            ><i class="charly-icon fa-solid fa-phone fa-xl"></i
            >06-82-53-68-07</a
          >
        </li>
      </ul>
    </div>
  </footer>
</template>

<script>
export default {
  name: "CharlyFooter",
  components: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.charly-footer {
  position: relative;
  display: grid;
  grid-template-columns: 65% 35%;
  padding: 64px 32px 128px 64px;

  &::before {
    content: "";
    display: block;
    width: 2px;
    height: calc(100% - 128px - 16px);
    background-color: #ce5334;
    box-shadow: 2px 2px 3px #00000045;
    position: absolute;
    top: 0;
    left: 0;
  }

  &::after {
    content: "";
    display: block;
    height: 2px;
    width: 600px;
    position: absolute;
    bottom: calc(128px + 16px);
    left: 0;
    background-color: #ce5334;
    box-shadow: 2px 2px 3px #00000045;
  }

  &__map-container {
    grid-column-start: 1;
    border-radius: 58px;
    padding: 36px;
    background: #fff;
    box-shadow: inset 3px 3px 2px #00000045;
    width: 650px;
    height: 300px;

    iframe {
      width: 100%;
      height: 100%;
      border: 0;
      border-radius: 27px;
      box-shadow: 3px 3px 2px #00000045;
    }
  }

  &__link-top-map {
    grid-column-start: 1;
    margin-bottom: 32px;
    margin-top: 64px;
  }

  &__shop-images {
    grid-column-start: 1;
    display: flex;
    margin: 0;
    padding: 0;
    z-index: 1;

    li {
      width: 170px;
      height: 128px;
      object-fit: cover;
      margin-right: 32px;

      &::marker {
        content: none;
      }

      img {
        width: 100%;
        height: 100%;
      }
    }
  }

  &__contacts {
    grid-row-start: 1;
    grid-column-start: 2;
    border-radius: 58px;
    box-shadow: inset 3px 3px 2px #00000045;
    padding: 36px;
    background: #fff;

    &__title {
      margin-left: 48px;
      text-transform: uppercase;
    }

    &__list {
      margin: 0;
      padding: 0;

      li {
        font-size: 14px;
        line-height: 30px;
        margin-bottom: 16px;

        .charly-icon {
          width: 40px;
          text-align: center;
          margin-right: 8px;
        }

        &::marker {
          content: none;
        }
      }
    }
  }
}
</style>
