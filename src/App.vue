<template>
  <div id="app" class="app">
    <levels></levels>
    <points-counter></points-counter>
  </div>
</template>

<script>
import Levels from "./components/Levels.vue"
import PointsCounter from './components/PointsCounter.vue'

export default {
  name: 'App',
  components: {
    Levels,
    PointsCounter
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;900&family=Roboto:wght@400;900&display=swap');
body {
  background-color: black;
}
.app {
  margin: 0 auto;
  display: flex;
  font-family: Roboto;
  color: white;
  min-width: 1320px;
  max-width: 1680px;
}
</style>
