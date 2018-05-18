<template>
  <div id="app">
    <RoadNum />
  </div>
</template>

<script>
import RoadNum from './components/RoadNum.vue'

export default {
  name: 'app',
  components: {
    RoadNum
  }
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
