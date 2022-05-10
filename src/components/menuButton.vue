<template>
  <div class="menu-button">
    <button @click="consoleMenuChange()" class="menu-element">
      {{ name }}
      <img v-if="isActive" src="./assets/to_down.png" alt="" />
      <img v-else src="./assets/to_up.png" alt="" />
    </button>
    <template v-if="isActive">
      <console-menu :objects="objects" />
    </template>
  </div>
</template>

<script>
import consoleMenu from "./consoleMenu.vue";

export default {
  components: {
    consoleMenu,
  },

  props: {
    isActive: {
      type: Boolean,
      required: false,
    },
    objects: {
      type: Array,
      required: false,
    },
    name: {
      type: String,
      required: false,
    },
  },

  methods: {
    consoleMenuChange() {
      this.$emit("open", this.name);
    },
  },
};
</script>
