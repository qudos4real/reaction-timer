<template>
   <p>Your reaction time was {{ score }} ms</p>
    <p>Previous results: {{ resultHistory }}</p>
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
   this.resultHistory.push(this.score);
}
}
</script>

<style>

</style>