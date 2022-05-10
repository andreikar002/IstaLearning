<template>
  <button class="menu-button container" @click="consoleMenuChange">
    <div class="colsole-lang-container container center">
      <img
        :src="require(`@/components/assets/${activeLang}pick.png`)"
        alt="#eror"
        class="langIMG"
      />
      <p class="console-lang-p">{{ activeLang }}</p>
    </div>
    <img v-if="isActive" src="./assets/to_down.png" alt="" class="langUp" />
    <img v-else src="./assets/to_up.png" alt="" class="langUp" />
    <template v-if="isActive">
      <div class="menu-console">
        <div
          v-for="lang in filteredLangs"
          :key="lang.name"
          class="menu-console-element"
        >
          <button
            @click="changeActiveLang(lang.name)"
            class="console-lang-item-container container center"
          >
            <div class="colsole-lang-container container center">
              <img
                :src="require(`@/components/assets/${lang.name}pick.png`)"
                alt="#eror"
                class="langIMG"
              />
              <p class="console-lang-p">{{ lang.name }}</p>
            </div>
          </button>
        </div>
      </div>
    </template>
  </button>
</template>

<script>
export default {
  data() {
    return {
      langs: [
        { name: "RUS" },
        { name: "ENG" },
        { name: "FRA" },
        { name: "GER" },
      ],
      activeLang: "ENG",
    };
  },
  props: {
    isActive: {
      type: Boolean,
      required: false,
    },
  },
  methods: {
    consoleMenuChange() {
      this.$emit("open", this.name);
    },
    changeActiveLang(name) {
      this.activeLang = name;
    },
  },

  computed: {
    filteredLangs() {
      return this.langs.filter((t) => t.name != this.activeLang);
    },
  },
};
</script>
