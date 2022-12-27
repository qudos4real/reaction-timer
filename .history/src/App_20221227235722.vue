<template>
 <h1>A Reaction Timer</h1>
 <button class="btn" @click="start" v-bind:disabled="isPlaying">Play</button>
 <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
 <Results v-if="showResult" :score="score"/>
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
      showResult: false,
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
.btn {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  font-size: 16px;
  cursor: pointer;
  border-radius: 10px;
}
.btn:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}
</style>
