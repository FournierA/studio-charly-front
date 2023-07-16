<template>
  <div id="content" class="charly-main">
    <CharlyHeader />
    <CharlyIntroduction />
    <div class="charly-main__highlight">
      <ServiceHighlight
        title="Portrait"
        description="Ce que j’aime dans la photo c’est de pouvoir <strong>capturer</strong> et <strong>transmettre les émotions</strong> en image. Ce qui fait du portrait ma passion, c’est l’infinité créative qu’il permet. Que ce soit en studio ou en extérieur, il permet de jouer avec les lumières, les décors, les accessoires pour <strong>obtenir l’image désirée</strong>. En couple, en famille ou même entre amis c’est un excellent moyen de conserver de beaux souvenirs."
        :pictures="portraits"
      />
    </div>
    <div class="charly-main__wedding">
      <ServiceCard
        variant="card"
        title="Mariage"
        description="Le mariage est une des étapes les plus importantes de la vie, chaque souvenir y est précieux. C’est pourquoi je peux vous accompagner de la préparation des mariés, à la cérémonie jusqu’au vin d’honneur, en passant par les photos des mariés. Je propose également des shootings en studio pour les faire-parts ou autres en fonction de vos envies. Je peux aussi fournir des accessoires tel que photobox."
        :images="['mariage.jpeg']"
      />
    </div>
    <div class="charly-main__birth">
      <ServiceCard
        variant="notebook"
        title="Grossesses, naissances et baptèmes"
        description="Quoi de plus merveilleux que d'<strong>accueillir un enfant</strong> dans sa famille? Je propose de vous accompagner dans cette période si joyeuse mais qui passe aussi si vite. De la grossesse au baptême en passant par la naissance, je prends le temps d’organiser des shootings à l'<strong>écoute de vos demandes</strong> pour garder des souvenirs inoubliables."
        :images="['naissance.jpeg']"
      />
    </div>
    <div class="charly-main__family">
      <ServiceCard
        variant="card-multiple"
        title="Famille"
        description="Puisqu’il n’y a pas besoin d’occasion pour vouloir <strong>garder des souvenirs</strong> de ses proches, je vous propose d’immortaliser votre famille au travers de shootings personnalisés."
        :images="['family_1.jpeg', 'family_2.jpeg']"
      />
    </div>
    <div class="charly-main__footer">
      <CharlyFooter />
    </div>
  </div>
</template>

<script>
import CharlyHeader from "@/components/CharlyHeader.vue";
import CharlyIntroduction from "@/components/CharlyIntroduction.vue";
import ServiceHighlight from "@/components/ServiceHighlight.vue";
import ServiceCard from "@/components/ServiceCard.vue";
import CharlyFooter from "@/components/CharlyFooter.vue";

export default {
  name: "App",
  components: {
    CharlyIntroduction,
    ServiceHighlight,
    ServiceCard,
    CharlyHeader,
    CharlyFooter,
  },
  computed: {
    portraits() {
      const images = this.importAll(
        require.context("./assets/portraits/", false, /\.(png|jpe?g|svg)$/)
      );

      return images;
    },
  },
  methods: {
    importAll(r) {
      return r.keys().map(r);
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,300;0,400;0,500;1,500&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Jost:wght@400&display=swap");
@import "normalize-scss";
@include normalize();

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  background-color: #f9f9f9f2;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Jost", sans-serif;
}

p,
header,
footer {
  font: normal 16px/30px "Roboto", sans-serif;
}

a {
  text-decoration: none;
  color: black;

  &:hover {
    text-decoration: underline;
  }
}

.container {
  max-width: 1440px;
  margin: auto;
}

.inner-container {
  max-width: 1139px;
  margin: auto;
}

.charly-main {
  &__highlight {
    background-color: rgb(285, 188, 176);
    margin-bottom: 95px;
    overflow: hidden;
  }

  &__wedding,
  &__family {
    margin-bottom: 96px;

    .service-card {
      width: 1241px;
      margin: auto;
    }
  }

  &__birth {
    background-color: rgb(285, 188, 176);
    margin-bottom: 96px;

    .service-card {
      padding: 40px;
      width: 1241px;
      margin: auto;
    }
  }

  &__footer {
    background-color: rgb(285, 188, 176);

    .charly-footer {
      width: 1241px;
      margin: auto;
    }
  }
}
</style>
