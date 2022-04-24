<template>
  <h1>Reaction Timer</h1>
  <button @click="start">Start</button>
  <div class="block">
    
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {},
  data() {
    return {
      isPlaying: false,
      delay: null

    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000 //returns number between 2000 and 7000
      console.log(this.delay);
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
