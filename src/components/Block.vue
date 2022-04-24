<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
     <p>click me</p> 
     <p>{{ seconds }} seconds</p>
     <p>{{ reactionTime }} reacted milisec</p>
  </div>
</template>

<script>
export default {
    props: ["delay"],
    data() {
        return {
            showBlock: false,
            seconds: this.mSecToSec(this.delay),
            timer: null,
            reactionTime: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer();
        }, this.delay);
    },
    updated() {
        console.log("updated");
    },
    methods: {
        mSecToSec(sec) {
            let str = Math.round(sec).toString();
            let firstChar = str[0];
            return firstChar + "," + str.substring(1,3);
        },
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10;
            },10);
        },
        stopTimer(){
            clearInterval(this.timer);
        }
    }

}
</script>

<style lang="scss" scoped>

    .block {
        display: flex;
        flex-direction: column; 
        justify-content: center;
        align-items: center;
        width: 15rem;
        height: 15rem;
        margin-top: 2rem;
        background: red;

        &:hover {
            cursor: pointer;
            outline: 2px solid black;
            transition: outline 0.1ms ;
        }
    }

</style>