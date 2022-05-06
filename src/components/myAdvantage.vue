<template>
  <div class="display-c center advantage">
    <img src="./assets/Ellipse13.png" alt="#eror" class="advantage-img" />
    <h2 class="main-color advantage-h" align="center">{{ h }}</h2>
    <p class="main-color advantage-p" align="center">{{ p }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },

  props: {
    h: {
      type: String,
      required: false,
    },
    p: {
      type: String,
      required: false,
    },
  },
};
</script>

<style src="./css/my-advantage.css"></style>
