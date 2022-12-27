<template>
    <div class="block" v-if="showBlock" @click="stopTimer">
        Click Me!
        </div>
</template>

<script>
import { react } from '@babel/types';

export default {
props: ['delay'],
data() {
    return {
        showBlock: false,
        timer: null,
        reactionTime: 0
    }
},
mounted() {
    setTimeout(() => {
        this.showBlock = true;
        startTimer()
    }, this.delay);
},
methods: {
  startTimer() {
    this.timer = setInterval (() => {
        this.reactionTime += 10;
        console.log(this.reactionTime);
    }, 10);
  },
  stopTimer() {
    this.showBlock = false;
    clearInterval(this.timer);
    console.log(this.reactionTime);
    // this.$emit('reaction-time', this.reactionTime);
  }
}
}
</script>

<style>
.block {
    width: 400px;
    border-radius: 20px;
    text-align: center;
    margin: 50px auto;
    line-height: 200px;
    background-color: green;
    color: white;
    font-size: 50px;
    cursor: pointer;
}
</style>