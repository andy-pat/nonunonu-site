<template>
  <div class="container">
    <img class="cloud2 cloud" src="../assets/cloud2.png" alt="" />

    <img class="cloud1 cloud" src="../assets/cloud1.png" alt="" />
    <div class="line_letters_box">
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
      function randomIntFromInterval(min, max) {
        var int = Math.floor(Math.random() * (max - min + 1) + min);
        return int;
      }
      var duration = randomIntFromInterval(3000, 5500);
      var delay = randomIntFromInterval(2000, 6000);
      anime({
        targets: [".cloud2", ".cloud1"],
        width: "100%",
        translateY: function () {
          return anime.random(0, 100);
        },
        scale: [0.4, 0.5, 0],
        opacity: [0, 0.8, 0.3],
        loop: true,
        alternate: true,
        duration: duration,
        easing: "easeInQuart",
        delay: anime.stagger(delay),
        loopComplete: function (anim) {
          duration = randomIntFromInterval(3000, 5500);
          delay = randomIntFromInterval(2000, 6000);
          const clouds = document.getElementsByClassName("cloud");

          for (let i = 0; i < clouds.length; i++) {
            clouds[i].style.top = Math.random() * 20 + "rem";
          }
        },
      });
      anime({
        targets: [".n1", ".o2", ".n3", ".u4", ".n5", ".o6", ".n7", ".u8"],
        translateX: 4,
        translateY: 10,
        rotate: 2,
        scale: [1.1],
        direction: "alternate",
        loop: true,
        duration: duration / 2,
        delay: anime.stagger(delay / 30),
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
        delay: duration / 2,
      });
    },
  },
};
</script>
<style lang="scss" scoped>
$top: random(20) + rem;
.line_letters_box {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
}
.letter_grid {
  display: grid;
  grid-template-columns: repeat(4, 6rem);
  grid-template-rows: repeat(2, 7rem);
  gap: 0rem;
  row-gap: 5rem;
  position: relative;
  left: 0rem;
  top: 9.5rem;
}

@media (min-width: 500px) {
  .letter_grid {
    grid-template-columns: repeat(8, 5rem);
    top: 12.5rem;

    display: flex;
    justify-content: center;
  }
  .svg_line2 {
    display: none;
  }
}
img {
  height: 7rem;
}

.svg_line1,
.svg_line2 {
  position: relative;
  width: max-content;
  font-weight: 30px;
  top: 15rem;
}

.svg_line2 {
  top: 23.8rem;
}
.cloud {
  z-index: 10;
}
.cloud2 {
  position: absolute;
  left: 0;
  top: $top;
  opacity: 0;
  rotate: 180deg;
}
.cloud1 {
  position: absolute;
  left: 0;
  top: $top -5rem;
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
