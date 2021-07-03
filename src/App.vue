<template>
  <div class="container">
    <Letters />
    <div class="buttons">
      <div class="gig-listings">
        <h1>upcoming gigs:</h1>
        <ul>
          <a href="https://mif.co.uk/whats-on/festival-square-8-july/">
            <li>Manchester International Festival 8th July 6.30pm</li>
          </a>
        </ul>
      </div>
      <!-- <button>Sound </button> -->
      <a href="https://www.youtube.com/watch?v=szddj-LsmW8" target="_blank">
        <button>Sound & Vision</button>
      </a>
      <a
        href="https://www.instagram.com/nonunonu_/"
        target="_blank"
        rel="noopener noreferrer"
      >
        <button>Vision</button>
      </a>
    </div>
  </div>
</template>

<script>
import Letters from "./components/Letters.vue";

export default {
  name: "App",
  components: {
    Letters,
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
  margin: 0;
  padding: 0;
  background-color: #3bd6e685;
  height: 100vh;
  width: 100vw;
  display: flex;
  overflow-x: hidden;
}

#app {
  width: max-content;
}

/* .container {
} */

.gig-listings {
  position: absolute;
  top: 0;
}

.buttons {
  display: flex;
  align-items: center;
  align-self: center;
  justify-content: space-around;
  width: 100%;
  margin-top: 2rem;
  button {
    width: 80px;
    height: 4rem;
    border: dotted 2px darkgreen;
    border-radius: 1rem;
    background-color: #c1aed2;
    font-family: Courier;
  }
}
</style>
