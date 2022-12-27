<template>
 <h1>A Reaction Timer</h1>
 <button>click me</button>
</template>

<script>


export default {
  name: 'App',
  components: {
    
  },
  data() {
    return {
      isPlaying: false,
      delay: 2000 + Math.random() * 5000,
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
