<template>
  <div id="app">
    <ChinaSeventy/>
    <Star/>
  </div>
</template>

<script>
import ChinaSeventy from './components/ChinaSeventy.vue'
import Star from './components/Star.vue'

export default {
  name: 'app',
  components: {
    ChinaSeventy,
    Star
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
}
</style>
