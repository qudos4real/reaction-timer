<template>
   <p>Your reaction time was {{ score }} ms</p>
   <p>That is {{ rank }}</p>
   <ul>
    <p v-if="resultList.length">Your previous scores:</p>
    <li v-for="result in resultList" :key="result">{{ result }} ms</li>
    <button class="btn reset" @click="resetScores">Reset scores</button>
  </ul>
</template>

<script>
export default {
props: ['score', 'resultList'],
data() {
   return {
    rank: null
   }
},
mounted() {
   if (this.score < 200) {
      this.rank = 'Amazing';
   } else if (this.score < 400) {
      this.rank = 'Good';
   } else if (this.score < 600) {
      this.rank = 'Not Bad';
   } else {
      this.rank = 'Bad';
   }
},
methods: {
   resetScores() {
      this.$emit('resetScores');
   }
},
}
</script>

<style>

</style>