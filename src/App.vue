<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from "./components/HelloWorld.vue";
import icon1 from "/assets/icon1.png";
import icon2 from "/assets/icon2.png";
import icon3 from "/assets/icon3.png";

import { ref } from "vue";

defineProps({
  msg: String,
});

const count = ref(0);

const icons = [
  {
    icon: icon1,
    label: "全球大牌",
    desc: "低至1折起",
  },
  {
    icon: icon2,
    label: "热门视频会员",
    desc: "充值5折起",
  },
  {
    icon: icon3,
    label: "会员零元购",
    desc: "好物好购",
  },
];
</script>

<template>
  <img class="banner" alt="Vue logo" src="/assets/banner.jpeg" />

  <div>
    <div class="top-icons">
      <div class="top-icon" v-for="(item, index) in icons" v-bind:key="index">
        <img class="top-icon-img" :src="item.icon" />
        <div class="top-icon-text">{{ item.label }}</div>
        <div class="top-icon-desc">{{ item.desc }}</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin: 0;
  width: 100%;
}

body * {
  max-width: 100%;
}

.banner {
  width: 100%;
  vertical-align: bottom;
}

.top-icons {
  margin: 0 auto;
  display: flex;
  align-items: center;
  background: #121315;
}

.top-icons .top-icon {
  flex: 1;
  margin: 0.625rem;

  .top-icon-img {
    width: 1.2rem;
  }

  .top-icon-text {
    margin-top: 0.25rem;
    font-weight: bold;
    font-size: 0.24rem;
    color: #ded3af;
  }

  .top-icon-desc {
    margin-top: 0.125rem;
    font-size: 0.24rem;
    color: #ded3af;
  }
}
</style>
