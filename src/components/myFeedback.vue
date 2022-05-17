<template>
  <div class="display-c feedback">
    <img src="./assets/feedback-top.png" alt="#eror" />
    <p>
      Consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
      dolore magna aliqua. consectetur adipiscing elit, sed do eiusmod tempor
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },

  props: {
    authorName: {
      type: String,
      required: false,
    },
    p: {
      type: String,
      required: false,
    },
    feedbackDate: {
      type: Date,
      required: false,
    },
    h: {
      type: String,
      required: false,
    },
  },
};
</script>

<style src="./css/my-feedback.css"></style>
