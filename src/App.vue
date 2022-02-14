<template>
  <Music />

</template>

<script>
import Music from './components/music-player.vue'


export default {
  name: 'App',
  setup() {
    return {
      message: 'Hello Vue!'
    }
  },
  components: {
    Music
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  padding: 0;
}

Music {
  margin: 0;
  padding: 0;
}
</style>
