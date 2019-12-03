<template>
  <div class="home">
    <Background></Background>
    <GameProgress></GameProgress>
    <AboutUs></AboutUs>
  </div>
</template>

<script>
import Background from '@/components/Background.vue'
import GameProgress from '@/components/GameProgress.vue'
import AboutUs from '@/components/AboutUs.vue'

export default {
  name: 'home',
  components: {
    Background,
    GameProgress,
    AboutUs
  }
}
</script>

<style scoped>
*{
  width: 100%;
  height: 100%;
}
</style>
