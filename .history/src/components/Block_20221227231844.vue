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
    // console.log(this.delay);
    setTimeout(() => {
        this.showBlock = true;
        startTimer()
    }, this.delay);
},
methods: {
  startTimer() {
    this.timer = setInterval (() => {
        this.reactionTime += 10;
    }, 10);
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