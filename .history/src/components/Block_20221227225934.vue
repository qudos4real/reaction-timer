<template>
    <div class="block" v-if="showBlock">
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
        Timer: null,
        reactionTime: 0
    }
},
mounted() {
    console.log(this.delay);
    setTimeout(() => {
        this.showBlock = true;
    }, this.delay)
},
methods: {
    clicked() {
        this.showBlock = false;
        this.reactionTime = Date.now() - this.Timer;
        this.$emit('reaction', this.reactionTime);
        console.log(this.reactionTime);
    }
},
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