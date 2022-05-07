<template>
  <button class="menu-button container" @click="isActive = !isActive">
    <img
      :src="require(`@/components/assets/${activeLang}pick.png`)"
      alt="#eror"
      class="langIMG"
    />
    <p class="lang-p">{{ activeLang }}</p>
    <img v-if="isActive" src="./assets/to_down.png" alt="" class="langUp" />
    <img v-else src="./assets/to_up.png" alt="" class="langUp" />
  </button>
  <template v-if="isActive">
    <div class="menu-console">
      <div v-for="lang in langs" :key="lang.name" class="menu-console-element">
        <div class="console-link-container">
          <img
            :src="require(`@/components/assets/${lang.name}pick.png`)"
            alt="#eror"
            class="langIMG"
          />
          <p class="lang-p">{{ lang.name }}</p>
        </div>
      </div>
    </div>
  </template>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
      langs: [
        { name: "RUS" },
        { name: "ENG" },
        { name: "FRA" },
        { name: "GER" },
      ],
    };
  },
  props: {
    activeLang: {
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
