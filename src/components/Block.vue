<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      click me
  </div>
</template>

<script>
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
        console.log('component mounted')
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
            console.log(this.delay)
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() =>{
                this.reactionTime += 10
                // console.log(this.timer)
            }, 10)
        },
        stopTimer() {
            // console.log(this.timer)
            clearInterval(this.timer)
            console.log(this.reactionTime)
        }
    }
    // updated() {
    //     console.log('component updated')
    // },
    // unmounted() {
    //     console.log('component unmounted')
    // }
}
</script>

<style>
    .block {
        width: 400px;
        background: green;
        color: white;
        padding: 100px;
        margin: 40px auto;
    }
</style>