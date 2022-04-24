<template>
  <div class="block" v-if="showBlock">
     <p>click me</p> 
     <p>{{ seconds }} seconds</p>
  </div>
</template>

<script>
export default {
    props: ["delay"],
    data() {
        return {
            showBlock: false,
            seconds: this.mSecToSec(this.delay)
        }
    },
    mounted() {
        console.log("mounted");
        setTimeout(() => {
            this.showBlock = true;
        }, this.delay);
    },
    updated() {
        console.log("updated");
    },
    unmounted() {},
    methods: {
        mSecToSec(sec) {
            let str = Math.round(sec).toString();
            let firstChar = str[0];
            return firstChar + "," + str.substring(1,3);
        }
    }

}
</script>

<style>
    .block{
        display: flex;
        flex-direction: column; 
        justify-content: center;
        align-items: center;
        width: 15rem;
        height: 15rem;
        margin-top: 2rem;
        background: red;
    }
</style>