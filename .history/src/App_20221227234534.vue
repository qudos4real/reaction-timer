<template>
 <h1>A Reaction Timer</h1>
 <button @click="start" v-bind:disabled="isPlaying">Play</button>
 <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
 <Results :score="score"/>
 <p v-if="showResult">Your reaction time was {{ score }} ms</p>
</template>

<script>
import Block from './components/Block.vue';
import Results from './components/Results.vue';

export default {
  name: 'App',
  components: {
    Block,
    Results
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false
    }
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 1000 + Math.random() * 4000;
      this.isPlaying = true;
      this.showResult = false;
    },
    endGame(reactionTime) {
      this.isPlaying = false;
      this.score = reactionTime;
      this.showResult = true;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
