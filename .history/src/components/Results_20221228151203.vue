<template>
  <p>Your reaction time was {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
  <div v-if="resultList.length" class="prevResults">
    <p class="scores">Your previous scores:</p>
    <ul>
      <li v-for="result in resultList" :key="result">{{ result }} ms</li>
    </ul>
    <button class="btn reset" @click="resetScores">Reset scores</button>
  </div>
</template>

<script>
export default {
  props: ["score", "resultList"],
  data() {
    return {
      rank: null,
      removeButton: false,
    };
  },
  mounted() {
    if (this.score < 100) {
      this.rank = "Very Fast Reaction!";
    } else if (this.score < 200) {
      this.rank = "Fast Reaction!";
    } else if (this.score < 300) {
      this.rank = "Average Reaction!";
    } else if (this.score < 400) {
      this.rank = "Slow Reaction!";
    } else {
      this.rank = "Very Slow Reaction!";
    }
  },
  methods: {
    resetScores() {
      this.$emit("resetScores");
    },
  },
};
</script>

<style>
.prevResults {
  width: 400px;
  margin: 0 auto;
  margin-top: 50px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 15px;
}
.prevResults > .reset {
  margin-top: 20px;
  font-size: 12px;
  padding: 5px 10px;
  border-radius: 5px;
  background-color: rgba(46, 172, 46, 0.727);
}
ul {
  list-style: decimal;
}
ul > li {
  margin: 5px 0;
}
.rank {
  font-size: 20px;
  font-weight: bold;
  margin-top: 20px;
}
</style>
