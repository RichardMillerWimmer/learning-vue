<template>
    <h3>Reaction time: {{  score  }}</h3>
    <h4>Your Rank: {{  rank }}</h4>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if (this.score < 250) {
            this.rank = "Ninja Fingers"
        } else if (this.score < 400) {
            this.rank = "Rapid Reflexes"
        } else {
            this.rank = "Snail pace..."
        }
    }
}
</script>

<style>

</style>