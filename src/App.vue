<template>
  <div>
    <my-header :width="width" />
    <div class="container center promo_clip">
      <div class="promo_clip-main">
        <h1>Lorem ipsum sit amet,</h1>
        <p>
          consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
          labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud
          exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        </p>
        <p>
          Duis aute irure dolor in reprehenderit in voluptate velit esse cillum
          dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non
          proident, sunt in culpa qui officia deserunt mollit anim id est
          laborum.
        </p>
        <button>Записаться</button>
      </div>
      <video src="./mp4/pinguins.mp4" controls="controls"></video>
    </div>
    <div class="block catalog">
      <h2 class="block-h">Каталог</h2>
      <div class="container grid-1 w-100 center wrap">
        <a href="#" class="catalog-element center">
          <img src="./assets/Rectangle47.png" alt="#eror" class="catalog-img" />
          <p class="catalog-font">Экскурсии-онлайн</p>
        </a>
        <a href="#" class="catalog-element center">
          <img src="./assets/Rectangle47.png" alt="#eror" class="catalog-img" />
          <p class="catalog-font">Экскурсии-онлайн</p>
        </a>
        <a href="#" class="catalog-element center">
          <img src="./assets/Rectangle47.png" alt="#eror" class="catalog-img" />
          <p class="catalog-font">Экскурсии-онлайн</p>
        </a>
      </div>
    </div>
    <div class="block advantages">
      <h2 class="block-h">Почему мы</h2>
      <div class="container wrap center grid-5">
        <my-advantage
          v-for="advantage in advantages"
          :key="advantage.h"
          :h="advantage.h"
          :p="advantage.p"
        />
      </div>
    </div>
    <div class="container center consult wrap" align="left">
      <h2>Записаться на консультацию</h2>
      <p class="consult-p" align="left">
        Пройдите анкетирование и запишитесь на 15-минутную консультацию с
        преподавателем
      </p>
      <a href="#">Пройти анкетирование</a>
    </div>
  </div>
</template>

<script>
import myAdvantage from "./components/myAdvantage.vue";
import myHeader from "./components/myHeader.vue";

export default {
  name: "App",
  components: {
    myHeader,
    myAdvantage,
  },
  created() {
    this.width = screen.width;
  },
  data() {
    return {
      width: 0,
      advantages: [
        {
          h: "Первое отличное преимущество",
          p: "consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, ",
        },
        {
          h: "Второе преимущество",
          p: "consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, ",
        },
        {
          h: "Третье преимущество",
          p: "consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, ",
        },
        {
          h: "Четвертое преимущество",
          p: "consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, ",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style src="./css/main.css"></style>
<style src="./css/main-page.css"></style>
