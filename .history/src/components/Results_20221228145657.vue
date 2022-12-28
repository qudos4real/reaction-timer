<template>
   <p>Your reaction time was {{ score }} ms</p>
   <p>{{ rank }}</p>
   <ul class="prevResults">
    <p v-if="resultList.length" class="scores">Your previous scores:</p>
    <li v-for="result in resultList" :key="result">{{ result }} ms</li>
    <button class="btn reset" @click="resetScores">Reset scores</button>
  </ul>
</template>

<script>
export default {
props: ['score', 'resultList'],
data() {
   return {
    rank: null,
    removeButton: false
   }
},
mounted() {
   if (this.score < 100) {
      this.rank = 'Very Fast Reaction!';
   } else if (this.score < 200) {
      this.rank = 'Fast Reaction!';
   } else if (this.score < 300) {
      this.rank = 'Average Reaction!';
   } else if (this.score < 400) {
      this.rank = 'Slow Reaction!';
   } else {
      this.rank = 'Very Slow Reaction!';
   };
},
methods: {
   resetScores() {
      this.$emit('resetScores');
   }
},
}
</script>

<style>
.prevResults{
   margin-top: 50px;
   padding: 10px;
   border: 1px solid #ccc;
   border-radius: 5px;
}
ul>.reset {
   margin-top: 20px;
   font-size: 10px;
   padding: 5px 10px;
   border-radius: 5px;
   background-color: #f44336;
}
ul {
   list-style: decimal;
}
ul>li {
   margin: 5px 0;
}

</style>