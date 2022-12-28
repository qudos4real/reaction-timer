<template>
   <p>Your reaction time was {{ score }} ms</p>
   <ul>
    <p v-if="resultList.length">Your previous scores:</p>
    <li v-for="result in resultList" :key="result">{{ result }} ms</li>
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
   this.rank = this.getRank();
},
methods: {
   getRank() {
     const sortedList = this.resultList.sort((a, b) => a - b);
     const rank = sortedList.indexOf(this.score) + 1;
     return rank;
   }
}
</script>

<style>

</style>