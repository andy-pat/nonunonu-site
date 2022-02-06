<template>
  <div class="container">
    <div class="buttons">
      <button @click="toggleModal">gigs</button>
      <a href="https://www.youtube.com/watch?v=szddj-LsmW8" target="_blank">
        <button><i class="fab fa-youtube"></i></button>
      </a>
      <a
        href="https://www.instagram.com/nonunonu_/"
        target="_blank"
        rel="noopener noreferrer"
      >
        <button><i class="fab fa-instagram"></i></button>
      </a>
    </div>
  </div>
  <Letters />
  <Gigs v-if="displayGigs" :gigs="gigs" @closeModal="toggleModal" />
</template>

<script>
import Letters from "./components/Letters.vue";
import Gigs from "./components/Gigs.vue";
export default {
  name: "App",
  components: {
    Letters,
    Gigs,
  },
  data() {
    return {
      displayGigs: false,
      gigs: [
        {
          venue: "Temple Of Art and Music",
          date: "22/02/22",
          link: "https://www.facebook.com/events/1197110244453739?ref=newsfeed",
        },
        {
          venue: "Fuel",
          link: "https://www.facebook.com/fuelcafebar/",
          date: "13/03/22",
        },
        {
          venue: "Matt & Phreds",
          date: "23/03/22",
        },
        {
          venue: "Revolver Liverpool",
          link: "https://revolverliverpool.co.uk/cavern-quarter-jazz/",
          date: "25/04/22",
        },
        {
          venue: "Manchester Jazz Festival",
          date: "24/05/22",
          link: "https://manchesterjazz.com/",
        },
        {
          venue: "Eskfest",
          date: "08/07/22",
        },
      ],
    };
  },
  methods: {
    toggleModal() {
      this.displayGigs = !this.displayGigs;
    },
  },
};
</script>

<style lang="scss">
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 0;
  background-color: #11187a85;
  margin: 0;
  height: 100%;
  overflow: hidden;
}

#app {
  width: 100%;
  height: 100%;
  overflow: hidden;
  position: static;
}

.gig-listings {
  position: absolute;
  top: 0;
}

.buttons {
  margin-top: 2rem;
  display: flex;
  padding: 0 3rem;
  justify-content: space-evenly;
  button {
    padding: 0.8rem;
    border: dotted 2px darkgreen;
    border-radius: 1rem;
    background-color: #c1aed2;
    font-family: Courier;
  }
}

@media only screen and (max-width: 500px) {
}
</style>
