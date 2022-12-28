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
   //  resultList: this.resultList,
    rank: null
   }
},

}
</script>

<style>

</style>