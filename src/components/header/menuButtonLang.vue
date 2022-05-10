<template>
  <div class="menu-button">
    <button @click="consoleMenuChange()" class="language">
      {{ activeLanguge }}
      <img v-if="isActive" src="./assets/to_down.png" alt="" />
      <img v-else src="./assets/to_up.png" alt="" />
    </button>
    <template v-if="isActive">
      <div class="menu-console">
        <div
          v-for="object in objects"
          :key="object.name"
          class="menu-console-element"
        >
          <div class="console-pick-container">
            <a href="#">
              {{ object.name }}
            </a>
          </div>
        </div>
      </div>
    </template>
  </div>
</template>

<script>
import consoleMenu from "./consoleMenu.vue";

export default {
  components: {
    consoleMenu,
  },
  created() {
    
  },
  data() {
    return {
      isActive: false,
      activeLanguge: { name: "RUS", img: "RUS 1" },
      languges: [
        { name: "RUS", img: "RUS 1" },
        { name: "ENG", img: "ENG 1" },
        { name: "FRA", img: "FRA 1" },
        { name: "GER", img: "GER 1" },
      ],
    };
  },
};
</script>

<style scoped>
.language {
  position: relative;
  text-decoration: none;
  border: none;
  font-size: calc((100vw - 300px) / (1140 - 300) * (15 - 10) + 13px);
}
.menu-console {
  display: inline-block;
  position: absolute;
  top: 8.2vh;
  margin-left: 1vw;
  padding: 1vh 0px 2vh 0px;
  background: rgba(248, 248, 248, 0.8);
  border: 2px solid #cbe2ef;
  box-sizing: border-box;
  border-radius: 15px;
  width: auto;
  max-width: 11.5vw;
  z-index: 2;
}
.menu-button {
  display: flex;
  flex-direction: column;
}
</style>
