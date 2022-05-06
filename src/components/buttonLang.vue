<template>
  <div class="menu-button container center w-100">
    <p class="lang-p">{{ name }}</p>
    <img v-if="isActive" src="./assets/to_down.png" alt="" />
    <img v-else src="./assets/to_up.png" alt="" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
    };
  },

  props: {
    name: {
      type: String,
      required: false,
    },
  },

  methods: {
    consoleMenuChange() {
      this.isActive = !this.isActive;
    },
  },
};
</script>
