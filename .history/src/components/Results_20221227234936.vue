<template>
   <p>Your reaction time was {{ score }} ms</p>
</template>

<script>
export default {
props: ['score',],
mounted() {
   console.log(this.score);
}
}
</script>

<style>

</style>