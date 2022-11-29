<template>
  <div id="content">
    <CharlyHeader />
    <CharlyIntroduction />
    <ServiceHighlight
      title="Portrait"
      description="Ce que j’aime dans la photo c’est de pouvoir <strong>capturer</strong> et <strong>transmettre les émotions</strong> en image. Ce qui fait du portrait ma passion, c’est l’infinité créative qu’il permet. Que ce soit en studio ou en extérieur, il permet de jouer avec les lumières, les décors, les accessoires pour <strong>obtenir l’image désirée</strong>. En couple, en famille ou même entre amis c’est un excellent moyen de conserver de beaux souvenirs."
    />
    <CharlyFooter />
  </div>
</template>

<script>
import CharlyHeader from "./components/CharlyHeader.vue";
import CharlyIntroduction from "./components/CharlyIntroduction.vue";
import ServiceHighlight from "./components/ServiceHighlight.vue";
import CharlyFooter from "./components/CharlyFooter.vue";

export default {
  name: "App",
  components: {
    CharlyIntroduction,
    ServiceHighlight,
    CharlyHeader,
    CharlyFooter
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;500&display=swap");
@import "normalize-scss";
@include normalize();

@font-face {
  font-family: "The Goldsmith Vintage";
  src: url("./assets/fonts/The_Goldsmith_Vintage/The_Goldsmith_Vintage.otf")
      format("otf"),
    url("./assets/fonts/The_Goldsmith_Vintage/The_Goldsmith_Vintage.ttf")
      format("ttf"),
    url("./assets/fonts/The_Goldsmith_Vintage/The_Goldsmith_Vintage.woff")
      format("woff"),
    url("./assets/fonts/The_Goldsmith_Vintage/The_Goldsmith_Vintage.woff2")
      format("woff2");
}

body {
  background-color:rgb(249, 249, 249);
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "The Goldsmith Vintage", sans-serif;
}

p, header, footer {
  font: normal 16px/30px "Roboto", sans-serif;
}

a {
    text-decoration: none;
    color:black;
  }

.container {
  width: 980px;
  margin: auto;
}
</style>
