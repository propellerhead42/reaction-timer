<template>
      <div v-if="showResults">
        <Results :score="score"></Results>
      </div>
  <div class="flex-container">
      <h1>Reaction Timer</h1>
      <button @click="start" :disabled="isPlaying">Start</button>
      <div v-if="isPlaying">
        <Block :delay="delay" @end="endGame"></Block>
      </div>
  </div>
</template>

<script>
  import Results from "./components/Results.vue";
  import Block from "./components/Block.vue";

  export default {
  name: 'App',
  components: {Block, Results},
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false

    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000; //returns number between 2000 and 7000
      this.isPlaying = true;
      this.showResults = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.flex-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  margin-bottom: 2rem;

  button{
    padding: 0.5rem 2rem;
   
    border: none;
    font: inherit;
    border-radius: 0.25rem;

    outline: 2px solid white;
    color: white;
    background: black;

    &:hover{
      cursor: pointer;
      outline: 2px solid black;
      color: black;
      background: white;

    }

    &:disabled {
      color: rgb(60, 60, 60);
      background: gray;
      cursor: none;

      &:hover {
        outline: none;
      }
    }

  }

}
</style>
