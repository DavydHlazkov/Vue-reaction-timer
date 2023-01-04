<template>
  <div>
    <h1 v-if="reactionTime <= 300">AWEEEEEEEESOME</h1>
    <h1 v-if="reactionTime <= 500 && reactionTime > 300">NICE</h1>
    <h1 v-if="reactionTime <= 700 && reactionTime > 500">GOOG</h1>
    <h1 v-if="reactionTime <= 900 && reactionTime > 700">NOT BAD</h1>
    <h1 v-if="reactionTime <= 1100 && reactionTime > 900">TRY BETTER</h1>
    <h1 v-if="reactionTime > 1100">WAKE UP!</h1>
    <h2>Your reaction time is: {{ reactionTime }} milliseconds</h2>
  </div>
</template>

<script>
export default {
  props: ["reactionTime"],
  data() {
    return {
      ratingPhrase: "",
    };
  },
};
</script>

<style></style>
