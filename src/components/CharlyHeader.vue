<template>
  <header class="charly-header inner-container">
    <!-- LOCATION -->
    <a
      class="charly-header__location"
      href="https://goo.gl/maps/LtAaLrWJzK26djqPA"
      target="blank"
    >
      26 rue Paul Machy, Bourbourg</a
    >

    <span class="charly-header__job-title">Photographe professionnel</span>

    <!-- LOGO -->
    <div class="charly-header__logo">
      <img :src="CharlyLogo" alt="Logo du Studio Charly" />
    </div>

    <!-- NAVIGATION -->
    <nav class="charly-header__navigation">
      <ul>
        <li><a href="#contacts">Contactez-moi</a></li>
        <!-- <li><a href="#">Mes tarifs</a></li> -->
      </ul>
    </nav>
  </header>
</template>

<script>
import CharlyLogo from "@/assets/logo.png";

export default {
  name: "CharlyHeader",
  components: {},
  setup() {
    return {
      CharlyLogo,
    };
  },
};
</script>

<style scoped lang="scss">
.charly-header {
  font: normal 14px/30px "Roboto", sans-serif;
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 48px;
  margin-bottom: 48px;
  border-bottom: 1px solid grey;

  &__location {
    position: relative;

    &::before {
      position: absolute;
      left: -25px;
      // CSS from Font Awesome documentation
      display: inline-block;
      font-style: normal;
      font-variant: normal;
      text-rendering: auto;
      -webkit-font-smoothing: antialiased;
      font-family: "Font Awesome 5 Free";
      font-weight: 900;
      content: "\f3c5";
    }
  }

  &__job-title {
    position: absolute;
    bottom: -35px;
    left: 50%;
    transform: translateX(calc(-150% - 20px));
  }

  &__logo {
    box-sizing: content-box;
    width: 130px;
    background: #f9f9f9f2;
    padding: 0 30px;
    position: absolute;
    left: 50%;
    top: 40px;
    transform: translateX(-50%);
  }

  &__job-title {
    color: #707070;
  }

  &__navigation {
    ul {
      list-style-type: none;
      display: flex;

      li {
        width: 120px;
        text-align: center;
      }
    }
  }
}
</style>
