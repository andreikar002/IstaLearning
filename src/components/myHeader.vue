<template>
  <div class="container header">
    <img src=".\assets\logo.png" alt="#eror" class="logo" />
    <template v-if="width > 660">
      <div class="container menu">
        <menu-button :objects="catalogObjects" :name="'Каталог'" />
        <menu-button :objects="aboutObjects" :name="'О нас'" />
        <a href="#" class="menu-element">Блог</a>
        <a href="#" class="menu-element">Контакты</a>
        <a href="#" class="button-gr">Войти</a>
      </div>
    </template>
    <template v-else>
      <div class="container grid-1 center">
        <a href="#" class="button-gr">Войти</a>
        <div class="display-c grid-1 gamburger">
          <button @click="gamburger = !gamburger" class="position-r">
            GAM
          </button>
          <template v-if="gamburger">
            <div
              class="display-c gamburger-menu position-a"
              :style="{ left: width - 80 + 'px' }"
            >
              <menu-button :objects="catalogObjects" :name="'Каталог'" />
              <menu-button :objects="aboutObjects" :name="'О нас'" />
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
import menuButton from "./menuButton.vue";

export default {
  components: {
    menuButton,
  },

  created() {
    this.width = screen.width;
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
    };
  },
};
</script>

<style src="./css/my-header.css"></style>
