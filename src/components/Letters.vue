<template>
  <div class="container">
    <img class="cloud2" src="../assets/cloud2.png" alt="" />

    <img class="cloud1" src="../assets/cloud1.png" alt="" />

    <img class="cloud3" src="../assets/cloud1.png" alt="" />
    <img class="cloud4" src="../assets/cloud2.png" alt="" />

    <svg
      class="svg_line1"
      width="100%"
      height="45"
      viewBox="0 0 380 24"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        class="line1"
        d="M0 1C41.25 19.738 306.136 22.2235 375 1"
        stroke="yellow"
        stroke-width="2"
      />
    </svg>
    <svg
      class="svg_line2"
      width="100%"
      height="45"
      viewBox="0 0 375 24"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        class="line2"
        d="M0 1C41.25 19.738 306.136 22.2235 375 1"
        stroke="red"
        stroke-width="2.2"
      />
    </svg>
    <div class="letter_grid">
      <div class="div">
        <img class="n1" src="../assets/n1.png" alt="" />
      </div>
      <div class="div">
        <img class="o2" src="../assets/o2.png" alt="" />
      </div>
      <div class="div">
        <img class="n3" src="../assets/n3.png" alt="" />
      </div>
      <div class="div">
        <img class="u4" src="../assets/u4.png" alt="" />
      </div>
      <div class="div">
        <img class="n5" src="../assets/n5.png" alt="" />
      </div>
      <div class="div">
        <img class="o6" src="../assets/o6.png" alt="" />
      </div>
      <div class="div">
        <img class="n7" src="../assets/n7.png" alt="" />
      </div>
      <div class="div">
        <img class="u8" src="../assets/u8.png" alt="" />
      </div>
    </div>
  </div>
</template>
<script>
import anime from "animejs";

export default {
  name: "letters",
  components: {},
  data() {
    return {
      animation: true,
    };
  },
  mounted() {
    this.animate();
  },
  methods: {
    animate() {
      anime({
        targets: [".n1", ".o2", ".n3", ".u4", ".n5", ".o6"],
        translateX: 4,
        translateY: 10,
        rotate: 2,
        scale: [1.1],
        direction: "alternate",
        loop: true,
        duration: 3000,
        delay: anime.stagger(100),
        easing: "easeOutInBounce",
      });
      anime({
        targets: [".cloud2", ".cloud1", ".cloud3", ".cloud4"],
        translateX: [-200, 300],
        scale: [0.4, 0.6, 0.3],
        opacity: [0, 0.8, 0],
        loop: true,
        // direction: "alternate",
        duration: 7000,
        easing: "easeInQuart",
        delay: anime.stagger(3500),
      });

      anime({
        targets: [".n5", ".o6", ".n7", ".u8"],
        translateX: 4,
        rotate: -3,
        translateY: 9,
        scale: [1.12],
        direction: "alternate",
        loop: true,
        duration: 3000,
        delay: anime.stagger(100),
        easing: "easeOutInBounce",
      });

      const linePath1 = "M0 1C41.25 19.738 306.136 22.2235 375 1";
      const linePath2 = "M0 1C10    22.5    320    30.5      375 1";
      linePath1;
      linePath2;
      anime({
        targets: [".line1", ".line2"],
        easing: "spring(1, 80, 10, 0)",
        direction: "alternate",
        duration: 3000,
        scale: 1.1,
        d: [{ value: linePath2 }, { value: linePath1 }],
        loop: true,
        delay: anime.stagger(300),
      });
    },
  },
};
</script>
<style>
.letter_grid {
  padding-top: 10rem;
  display: grid;
  grid-template-columns: repeat(4, 6rem);
  grid-template-rows: repeat(2, 7rem);
  gap: 0rem;
  row-gap: 5rem;
  justify-content: center;
  position: absolute;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  text-align: center;
}

.line {
  position: absolute;
  left: 0;
  top: 4rem;
  width: 100%;
}

img {
  height: 7rem;
}
.svg_line1,
.svg_line2 {
  position: absolute;
  left: 0;
  top: 9.7rem;
  width: max-content;
  position: absolute;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  text-align: center;
}

.svg_line2 {
  top: 21.8rem;
}

.cloud2 {
  position: absolute;
  left: 0;
  top: 6rem;
  opacity: 0;
  rotate: 180deg;
}
.cloud1 {
  position: absolute;
  left: 0;
  top: 14rem;
  opacity: 0;
}

.cloud3 {
  position: absolute;
  left: 0;
  top: 16rem;
  opacity: 0;
  rotate: 180deg;
}
.cloud4 {
  position: absolute;
  left: 0;
  bottom: 9rem;
  opacity: 0;
}

ul {
  list-style-type: none;
}

@media only screen and (max-width: 500px) {
  .svg_line1,
  .svg_line2 {
    width: 100%;
  }
}
</style>
