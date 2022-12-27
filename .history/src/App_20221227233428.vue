<template>
 <h1>A Reaction Timer</h1>
 <button @click="start" v-bind:disabled="isPlaying">click me</button>
 <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
 <p>Your reaction time was {{ score }} ms</p>
</template>

<script>
import Block from './components/Block.vue';

export default {
  name: 'App',
  components: {
    Block
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null
    }
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
    },
    endGame(reactionTime) {
      this.isPlaying = false;
      this.score = reactionTime;
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
