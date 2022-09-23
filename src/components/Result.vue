<template>
    <h1 class="results">Reaction Time : {{ result }} ms</h1>
    <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
    props: ['result'],
    data() {
        return  {
            rank: null
        }
    },
    mounted() {
        if(this.result < 250) {
            this.rank = "Reflexes Emperor"
        } else if (this.result < 400)  {
            this.rank = "Rapid Reflexes"
        } else {
            this.rank = "Snail Pace..."
        }
    }
}
</script>

<style>
    .results { 
        text-align: center;
        margin-top: 50px;
    }
    .rank {
        font-size: 1.dem;
        color: #0faf87;
        font-weight: bold;
    }
</style>