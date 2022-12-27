<template>
    <div class="block" v-if="showBlock">
        Click Me!
        </div>
</template>

<script>
export default {
props: ['delay'],
data() {
    return {
        showBlock: false,
    }
},
mounted() {
    console.log(this.delay);
    setTimeout(() => {
        this.showBlock = true;
    }, 1000)
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