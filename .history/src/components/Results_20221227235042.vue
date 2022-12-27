<template>
   <p>Your reaction time was {{ score }} ms</p>
</template>

<script>
export default {
props: ['score',],
data() {
   return {
    resultHistory: [],
   }
},
mounted() {
   console.log(this.score);
   this.resultHistory.push(this.score);
}
}
</script>

<style>

</style>