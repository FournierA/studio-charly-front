<template>
  <div class="charly-introduction container">
    <div class="charly-introduction__left">
      <h2 class="charly-introduction__title">Qui suis-je ?</h2>
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
      <!-- <figcaption>
        <h3>
          "Photographier, c'est une attitude, une façon d'être, une manière de
          vivre"
        </h3>
        Henri Cartier Bresson
      </figcaption> -->
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
  display: flex;
  margin: 128px auto;

  &__left {
    position: relative;
    text-align: center;
    width: 50%;
    padding: 32px 0;
    border-top: 1px solid grey;
    border-bottom: 1px solid grey;
  }

  &__right {
    width: 50%;
    margin: 0 auto 0 32px;
  }

  &__title {
    position: absolute;
    top: 0;
    left: 50%;
    margin: 0;
    transform: translate(-50%, -50%);
    background: white;
    border: 32px solid white;
    border-radius: 48px;
  }

  &__paragraph {
    text-align: left;
  }

  &__read-more-button {
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translate(-50%, 50%);
    color: white;
    display: block;
    background: #bf5b3e;
    border-radius: 48px;
    padding: 12px 48px;
    margin: auto;
    border: 32px solid white;

    &::after {
      content: "";
      display: block;
      position: absolute;
      background: blue;
      width: 100%;
      top: 0;
      left: 0;
    }
  }
}
</style>
