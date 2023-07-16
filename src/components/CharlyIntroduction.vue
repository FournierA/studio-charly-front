<template>
  <div class="charly-introduction inner-container">
    <div class="charly-introduction__left">
      <h2 class="charly-introduction__title">Qui je suis ?</h2>
      <p class="charly-introduction__paragraph">
        Je m’appelle Charly, c’est pendant mon enfance qu’est née
        <strong>ma passion pour la photo</strong>, en photographiant les
        personnes de mon quartier avec mon polaroid. Puis, avec le temps, je
        suis passé au reflex argentique pour finir par du matériel numérique.
      </p>
      <p class="charly-introduction__paragraph">
        C’est <strong>cette expérience et cette passion</strong> que je mets au
        service de mes clients et de leurs envies. Il est important pour moi de
        prendre le temps de discuter et d’échanger avec les modèles pour offrir
        <strong>une prestation de qualité et en toute confiance</strong>.
      </p>
      <p v-if="seeMoreActive" class="charly-introduction__paragraph">
        Je propose des shootings portraits, en studio ou en extérieur, seul, en
        couple ou en famille. Je peux vous accompagner dans les grands
        événements de la vie tels que des mariages, des naissances, des
        grossesses, ou encore des baptêmes et EVJF. Je peux également couvrir
        des concerts, rassemblements, concours, team building, ect…
      </p>
      <p v-if="seeMoreActive" class="charly-introduction__paragraph">
        Mes services comprennent également les photos d'identité, de passeport
        ou permis, mais aussi les E-photo ANTS avec un logiciel agréé.
      </p>
      <button
        type="submit"
        class="charly-introduction__read-more-button"
        @click="toggleSeeMore"
      >
        {{ seeMoreLabel }}
      </button>
    </div>

    <figure class="charly-introduction__right">
      <img src="../assets/charly.png" />
      <figcaption>
        <h3>
          "Photographier, c'est une attitude, une façon d'être, une manière de
          vivre"
        </h3>
        Henri Cartier Bresson
      </figcaption>
    </figure>
  </div>
</template>

<script>
export default {
  name: "CharlyIntroduction",
  components: {},
  data() {
    return {
      seeMoreActive: false,
    };
  },
  computed: {
    seeMoreLabel() {
      return this.seeMoreActive ? "En lire moins" : "En lire plus";
    },
  },
  methods: {
    toggleSeeMore() {
      this.seeMoreActive = !this.seeMoreActive;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.charly-introduction {
  display: grid;
  grid-template-columns: 50% 50%;
  margin: 192px auto;

  &__left {
    position: relative;
    text-align: center;
    padding: 76px 0;
    min-height: 480px;
  }

  &__right {
    margin: 0 auto 0 32px;
    position: relative;

    img {
      height: 480px;
      box-shadow: 2px 2px 5px #00000045;
      border-radius: 6px;
    }

    figcaption {
      position: absolute;
      top: -90px;
      left: 175px;
      width: 400px;
      color: #707070;
      font: 300 20px/26px "Roboto", sans-serif;
      text-align: center;

      h3 {
        font: italic 500 20px/26px "Roboto", sans-serif;

        &::after {
          content: "";
          position: absolute;
          display: block;
          height: 3px;
          width: 220px;
          background-color: #ce5334;
          left: 146px;
        }
      }
    }
  }

  &__title {
    position: absolute;
    top: 0;
    left: 50%;
    transform: translate(-50%, -50%);
    margin: 0;
    text-align: center;
    background: #f9f9f9;
    border-radius: 48px;
    font-size: 30px;
    line-height: 60px;
    letter-spacing: 0.9px;

    &::before {
      content: "";
      position: absolute;
      background: grey;
      height: 1px;
      top: 50%;
      left: -106%;
      width: 170px;
    }

    &::after {
      content: "";
      position: absolute;
      background: grey;
      height: 1px;
      top: 50%;
      right: -106%;
      width: 170px;
    }
  }

  &__paragraph {
    text-align: left;
  }

  &__read-more-button {
    cursor: pointer;
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translate(-50%, 50%);
    color: white;
    display: block;
    background: #bf5b3e;
    border-radius: 28px;
    border-color: transparent;
    padding: 12px 48px;
    box-shadow: 3px 3px 2px #00000045;

    &::before {
      content: "";
      position: absolute;
      background: grey;
      height: 1px;
      top: 50%;
      left: -112%;
      width: 170px;
    }

    &::after {
      content: "";
      position: absolute;
      background: grey;
      height: 1px;
      top: 50%;
      right: -112%;
      width: 170px;
    }

    &:hover {
      background-color: #9a4932;
    }
  }
}
</style>
