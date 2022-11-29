<template>
  <header class="charly-header">  
    <nav>    
      <a href="#"><i class="fa-solid fa-location-dot fa-lg"></i> 26 rue Paul Machy, Bourbourg</a>
      <ul style="float:right">
        <li id="services"><a href="">Contactez-moi</a> </li>
        <li id="contact" style="padding-right: 10px;"><a href="">Mes tarifs</a> </li>
      </ul>
    </nav>
    <ul>
      <li class="charly-header__left"><p style="float:right">Photographe professionnel</p></li>
      <li><img id="logo" src="../assets/logo.jpg" alt="logo"></li>
    </ul>
  </header>
</template>

<script>
export default {
  name: "CharlyHeader",
  components: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.charly-header {
  margin: 5% 18%;
  font-weight: 500;

  nav {
    border-bottom: 2px solid rgb(189, 189, 189);
    padding-bottom:10px;
  }

  nav>a {
    margin-left:-3%;
  }

  ul {
    overflow: hidden;
    list-style-type: none;
    margin: 0;
    padding: 0;
  }

  li {
    display: inline-block;
    padding-left:50px;
  }

  &__left {
    width:50%;
    margin-top: -12px;
    color:rgb(152, 152, 152);
  }

  &__left p {
    margin-right:165px;
  }

  #logo {
    width: 150px;
    position: absolute;
    top: 100px;
    left: 50%;
    margin: 0;
    transform: translate(-50%, -50%);
    border: 32px solid rgb(249, 249, 249);
    border-radius: 48px;
  }
  
  i.fa-solid {
    width:25px;
  }
}
</style>
