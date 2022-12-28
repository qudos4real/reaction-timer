<template>
   <p>Your reaction time was {{ score }} ms</p>
   <p>That is {{ rank }}</p>
   <ul>
    <p v-if="resultList.length" class="scores">Your previous scores:</p>
    <li v-for="result in resultList" :key="result">{{ result }} ms</li>
    <button v-if="removeButton" class="btn reset" @click="resetScores">Reset scores</button>
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
   if (this.score < 200) {
      this.rank = 'Fast Reaction!';
   } else if (this.score < 400) {
      this.rank = 'Good Reaction!';
   } else if (this.score < 600) {
      this.rank = 'Not Bad Reaction!';
   } else {
      this.rank = 'Bad Reaction!';
   }
},
methods: {
   resetScores() {
      this.$emit('resetScores');
      this.removeButton = true;
   }
},
}
</script>

<style>
ul>.reset {
   margin-top: 20px;
   font-size: 10px;
   padding: 5px 10px;
   border-radius: 5px;
   background-color: #f44336;
}
ul {
   list-style: none;
   padding: 0;
}
ul>li {
   margin: 5px 0;
}

</style>