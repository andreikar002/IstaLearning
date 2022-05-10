<template>
  <div class="container header">
    <img src=".\assets\logo.png" alt="#eror" class="logo" />
    <template v-if="width > 620">
      <div class="container menu">
        <menu-button
          :objects="catalogObjects"
          :name="'Каталог'"
          :isActive="isOpened.catalog"
          @open="openConsole('catalog')"
        />
        <menu-button
          :objects="aboutObjects"
          :name="'О нас'"
          :isActive="isOpened.about"
          @open="openConsole('about')"
        />
        <a href="#" class="menu-element">Блог</a>
        <a href="#" class="menu-element">Контакты</a>
        <button-lang @open="openConsole('lang')" :isActive="isOpened.lang" />
        <a href="#" class="button-gr">Войти</a>
      </div>
    </template>
    <template v-else>
      <div class="menu container center">
        <button-lang @open="openConsole('lang')" :isActive="isOpened.lang" />
        <a href="#" class="button-gr">Войти</a>
        <div class="display-c grid-1 gamburger">
          <button @click="openConsole('gamburger')" class="position-r">
            <img
              src="./assets/hamburger.png"
              alt="#eror"
              class="gamburger-img"
            />
          </button>
          <template v-if="gamburger">
            <div
              class="display-c center gamburger-menu position-a"
              :style="{ left: width - 80 + 'px' }"
            >
              <menu-button
                :objects="catalogObjects"
                :name="'Каталог'"
                :isActive="isOpened.catalog"
                @open="openConsole('catalog')"
              />
              <menu-button
                :objects="aboutObjects"
                :name="'О нас'"
                :isActive="isOpened.about"
                @open="openConsole('about')"
              />
              <a href="#" class="menu-element">Блог</a>
              <a href="#" class="menu-element">Контакты</a>
            </div>
          </template>
        </div>
      </div>
    </template>
  </div>
</template>

<script>
import ButtonLang from "./buttonLang.vue";
import menuButton from "./menuButton.vue";
export default {
  components: {
    menuButton,
    ButtonLang,
  },

  created() {
    this.width = screen.width;
    window.addEventListener("resize", this.updateWidth);
  },

  computed: {
    screenWidth() {
      return screen.width;
    },
  },
  data() {
    return {
      languages: ["RUS", "ENG", "GER", "FRA"],
      activeLanguge: "ENG",
      width: 0,
      gamburger: false,
      catalogObjects: [
        {
          link: "#",
          name: "object1",
        },
        {
          link: "#",
          name: "object2",
        },
        {
          link: "#",
          name: "object3",
        },
        {
          link: "#",
          name: "object4",
        },
      ],
      aboutObjects: [
        {
          link: "#",
          name: "object",
        },
        {
          link: "#",
          name: "object2",
        },
        {
          link: "#",
          name: "object3",
        },
        {
          link: "#",
          name: "object4",
        },
      ],
      isOpened: {
        catalog: false,
        about: false,
        lang: false,
      },
    };
  },
  methods: {
    updateWidth() {
      this.width = screen.width;
    },
    openConsole(name) {
      if (name === "catalog") {
        this.isOpened.catalog = !this.isOpened.catalog;
        this.isOpened.about = false;
        this.isOpened.lang = false;
      }
      if (name === "about") {
        this.isOpened.about = !this.isOpened.about;
        this.isOpened.catalog = false;
        this.isOpened.lang = false;
      }
      if (name === "lang") {
        this.isOpened.lang = !this.isOpened.lang;
        this.isOpened.catalog = false;
        this.isOpened.about = false;
        this.gamburger = false;
      }
      if (name === "gamburger") {
        this.gamburger = !this.gamburger;
        this.isOpened.catalog = false;
        this.isOpened.about = false;
        this.isOpened.lang = false;
      }
    },
  },
};
</script>

<style src="./css/my-header.css"></style>
