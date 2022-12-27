<template>
   <p v-if="showResult">Your reaction time was {{ score }} ms</p>
</template>

<script>
export default {
props: ['score',],
}
</script>

<style>

</style>