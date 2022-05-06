<template>
  <div class="menu-console">
    <div
      v-for="object in objects"
      :key="object.name"
      class="menu-console-element"
    >
      <div class="console-link-container">
        <a href="#">
          {{ object.name }}
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },

  props: {
    objects: {
      type: Array,
      required: false,
    },
  },
};
</script>
