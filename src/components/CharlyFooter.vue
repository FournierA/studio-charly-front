<template>
  <footer class="charly-footer__container">
      <div class="charly-footer__map-contacts">
        <div class="charly-footer__map-photos">
          <div class="charly-footer__map">
            <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2513.8470072822574!2d2.1947512156350513!3d50.94504237954659!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47dc5ef733edb497%3A0x9c3df032d42f1ad2!2s26%20Rue%20Paul%20Machy%2C%2059630%20Bourbourg!5e0!3m2!1sfr!2sfr!4v1669729618896!5m2!1sfr!2sfr" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            <a href="#"><i class="fa-solid fa-location-dot fa-xl"></i> 26 rue Paul Machy, Bourbourg</a>
          </div>
          <div class="charly-footer__studio">
            <img class="charly-footer__img" src="../assets/studio/studio.jpg" alt="Devanture du studio">
            <img class="charly-footer__img" src="../assets/studio/frontDesk.jpg" alt="Accueil">
            <img src="../assets/studio/shootingSpace.jpg" alt="Espace shooting">
          </div>
        </div>
        <div class="charly-footer__contacts">
          <h2 class="charly-footer__title">CONTACTS</h2>
          <div class="charly-footer__social-networks">
            <a href=""><i class="fa-brands fa-instagram fa-2xl"></i> @studio_charly_photo</a>
            <a href=""><i class="fa-brands fa-facebook-f fa-xl"></i> Studio Charly</a>
            <a href=""><i class="fa-brands fa-linkedin fa-2xl"></i> Charly Photographe</a>
            <a href=""><i class="fa-regular fa-envelope fa-2xl"></i> studio.charly.bourgourg@gmail.com</a>
          </div>
        </div>
      </div>
      <div class="charly-footer__links">
          <a href="">Accueil</a>
          <a href="">Contactez-moi</a>
          <a href="">Mes tarifs</a>
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
  &__container {
    background-color: rgb(232,186,174);
    width: 80%;
    margin: 0 10%;
  }

  //dimensions map, pictures and orangy background
  &__map iframe {
    height: 220px;
    width: 570px;
    margin-bottom: 10px;
  }

  &__map a {
  margin-bottom: 30px;
  }

  &__studio img {
    width: 170px;
    height: 130px;
  }

  &__links {
    background-color: rgb(206,83,52);
    width: calc(100%-57px);
    height: 122px;
    margin-right: 15px;
    margin-left: 3.5%; //42px
    padding-left: 6%;
    margin-bottom:0;
  }

  //network icons
  &__social-networks .fa-brands, &__social-networks .fa-regular, &__map .fa-solid  {
    padding-right: 15px;
  }

  &__social-networks .fa-facebook-f {
    padding-right: 25px;
    padding-left: 7px;
  }

  &__social-networks .fa-linkedin {
    padding-right: 17px;
    padding-left: 2px;
  }

//Google Maps & studio
  &__map-contacts {
    display: flex;
    justify-content: center;
    padding-top: 37px;
    font-weight: 600;
  }

  &__map {
    display: flex;
    flex-direction: column;
  }

  &__studio {
    margin-bottom: 40px;
  }

  &__img {
    margin-right: 30px;
  }

  //contacts
  &__title {
    margin-top: 0;
    margin-left: 48px;
    margin-bottom: 60px;
    font-size: 2em;
    font-weight: 500;
  }

  &__social-networks {
    display: flex;
    flex-direction: column;
  }

  &__social-networks a {
    margin-bottom: 30px;
  }

  &__contacts {
    padding-left: 8%;
  }

  &__links {
    display:flex;
    flex-direction: column;
    padding-top:18px;
  }
}
</style>
