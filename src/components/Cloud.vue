<template>
  <div class="container" @click="animate">
    <img class="cloud1" src="../assets/cloud1.png" alt="" />
  </div>
</template>
<script lang="ts">
import anime from "animejs";

export default {
  name: "cloud",
  data() {
    return {
      animation: true,
    };
  },
  methods: {
    animate() {
      anime({
        targets: ".cloud1",
        translateX: [500, 0],
        // translateY: [0, 1, -1, 2, -2, 1, -1, 0],
        baseFrequency: 0,
        scale: 1,
        loop: true,
        direction: "alternate",
        easing: "easeInOutExpo",
        delay: anime.stagger(100),
      });
    },
  },
};
</script>
<style lang="scss">
img {
  height: 100px;
  //   position: absolute;
  top: 30px;
}
</style>
