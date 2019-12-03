<template>
  <div class="main-image">
    <!-- <img src="/imgs/vida4.jpg" alt="">
    <figcaption>Bodas de Video Game</figcaption>
    <figcaption>
      <img src="http://nilethemes.com/html/zawag/assets/rslider/assets/e7b73-top-line.png" alt="">
    </figcaption> -->

    <div class="contents">
      <img class="effects-top-image" src="http://nilethemes.com/html/zawag/assets/rslider/assets/e7b73-top-line.png" alt="">
      <p>BODAS DE VIDEO GAME 🎮</p>
      <p class="names">Felipecss & Tatiana</p>
      <img class="effects-down-image" src="http://nilethemes.com/html/zawag/assets/rslider/assets/e7b73-top-line.png" alt="">
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.main-image {
  background-image: url(/imgs/vida4.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center center;
  width: 100%;
  height: 100%;
  opacity: 0.7;
  visibility: visible;
  z-index: 20;
}

.main-image p {
  position: relative;
  font-family: 'Fugaz One', cursive;
  top: 0;
  right: 0;
  color: #fff;
  text-shadow: 10px 3px 5px black;
}
.names {
  font-family: 'Fugaz One', cursive;
  font-size: 80px;
  font-style:
}
.effects-down-image{
  margin-bottom: 350px
}
.contents{
    position: relative;
    top: 86px;
    left: 1px;
}
/* .main-image {
  display: inline-block;
  position: relative;
}
.main-image img {
  width: 100%;
  height: 100%;
  opacity: 0.5;
}

.main-image figcaption {
  position: absolute;
  top: 0;
  right: 0;
  font-size: 40px;
  color: black;
  text-shadow: 0px 0px 5px black;
} */
</style>