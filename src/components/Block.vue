<template>
  <div v-if="showBlock" class="block" @click="stopTimer"><p>click me</p></div>
</template>

<script>
export default {
  props: ["delay"],
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit("end", this.reactionTime);
    },
  },
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
};
</script>

<style>
.block {
  width: 300px;
  height: 300px;
  border-radius: 100%;
  background: #f2f4f4;
  color: #5d6d7e;
  text-align: center;
  margin: 150px auto;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}
.block p {
  font-size: 25px;
  font-weight: 700;
  color: #2e4053;
}
</style>
