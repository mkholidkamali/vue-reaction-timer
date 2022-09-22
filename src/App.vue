<template>
  <h1>Kk Reaction Timer</h1>
  <button class="play" @click="start" :disabled="isPlaying">PLAY</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame"></Block>
  <Result v-if="showResult" :result="score"></Result>
</template>

<script>
import Block from "./components/Block.vue"
import Result from "./components/Result.vue"

export default {
  name: "App",
  components: { Block, Result },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false
    }
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000,
      this.isPlaying = true
      this.showResult = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResult = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
.play {
  color: white;
  background: teal;
  padding: 10px 20px;
  border-radius: 5px;
  border: 0px;
}
.play:disabled {
  background: rgba(0, 0, 0, 0.5);
  color: rgba(0, 0, 0, 0.5);
  z-index: -1;
}
</style>
