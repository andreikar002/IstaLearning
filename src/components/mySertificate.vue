<template>
  <a href="#" class="container center sertificate">
    <img
      :src="require(`@/components/assets/sertificate${sertificateNum}.png`)"
      alt="#eror"
    />
  </a>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    sertificateNum: {
      type: Number,
      required: false,
    },
  },
  methods: {},
};
</script>

<style src="./css/my-sertificate.css"></style>
