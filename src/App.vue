<template>
  <h1>Timer Game</h1>
  <Results :reactionTime="reactionTime" v-if="showResult" />
  <button @click="start" :disabled="isPlaying">PLAY</button>
  <Block v-if="isPlaying" :delay="delay" @end="getReactionTime" />
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";
export default {
  name: "App",
  data() {
    return {
      isPlaying: false,
      delay: null,
      reactionTime: null,
      showResult: false,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResult = false;
    },
    getReactionTime(reactionTime) {
      this.reactionTime = reactionTime;
      this.isPlaying = false;
      this.showResult = true;
    },
  },
  components: { Block, Results },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #5d6d7e;
  margin-top: 60px;
}
h1 {
  font-size: 50px;
}
button {
  width: 150px;
  height: 50px;
  border: none;
  border-radius: 7px;
  background: #d4efdf;
  font-size: 20px;
  color: #5d6d7e;
  font-weight: 900;
  cursor: pointer;
  margin-top: 50px;
}
</style>
