<template>
  <div class="">
    <div class="gradient shape"></div>
    <Letters></Letters>
    <Gigs v-if="showGigs" @closeModal="showGigs = false" :gigs="gigs" />
    <div class="buttons">
      <a href="https://www.youtube.com/watch?v=szddj-LsmW8" target="_blank">
        <button>
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
            <path
              d="M549.655 124.083c-6.281-23.65-24.787-42.276-48.284-48.597C458.781 64 288 64 288 64S117.22 64 74.629 75.486c-23.497 6.322-42.003 24.947-48.284 48.597-11.412 42.867-11.412 132.305-11.412 132.305s0 89.438 11.412 132.305c6.281 23.65 24.787 41.5 48.284 47.821C117.22 448 288 448 288 448s170.78 0 213.371-11.486c23.497-6.321 42.003-24.171 48.284-47.821 11.412-42.867 11.412-132.305 11.412-132.305s0-89.438-11.412-132.305zm-317.51 213.508V175.185l142.739 81.205-142.739 81.201z"
            />
          </svg>
        </button>
      </a>
      <button @click="showGigs = !showGigs" @mouseenter="animate">
        <!-- <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
          <path
            d="M160 32V64H288V32C288 14.33 302.3 0 320 0C337.7 0 352 14.33 352 32V64H400C426.5 64 448 85.49 448 112V160H0V112C0 85.49 21.49 64 48 64H96V32C96 14.33 110.3 0 128 0C145.7 0 160 14.33 160 32zM0 192H448V464C448 490.5 426.5 512 400 512H48C21.49 512 0 490.5 0 464V192zM64 304C64 312.8 71.16 320 80 320H112C120.8 320 128 312.8 128 304V272C128 263.2 120.8 256 112 256H80C71.16 256 64 263.2 64 272V304zM192 304C192 312.8 199.2 320 208 320H240C248.8 320 256 312.8 256 304V272C256 263.2 248.8 256 240 256H208C199.2 256 192 263.2 192 272V304zM336 256C327.2 256 320 263.2 320 272V304C320 312.8 327.2 320 336 320H368C376.8 320 384 312.8 384 304V272C384 263.2 376.8 256 368 256H336zM64 432C64 440.8 71.16 448 80 448H112C120.8 448 128 440.8 128 432V400C128 391.2 120.8 384 112 384H80C71.16 384 64 391.2 64 400V432zM208 384C199.2 384 192 391.2 192 400V432C192 440.8 199.2 448 208 448H240C248.8 448 256 440.8 256 432V400C256 391.2 248.8 384 240 384H208zM320 432C320 440.8 327.2 448 336 448H368C376.8 448 384 440.8 384 432V400C384 391.2 376.8 384 368 384H336C327.2 384 320 391.2 320 400V432z"
          />
        </svg> -->

        <svg
          xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
          xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          xmlns:ns1="http://sozi.baierouge.fr"
          xmlns:cc="http://creativecommons.org/ns#"
          xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
          xmlns:dc="http://purl.org/dc/elements/1.1/"
          id="Layer_1"
          xml:space="preserve"
          version="1.1"
          viewBox="0 0 325.594 368.981"
          inkscape:version="0.91 r13725"
        >
          <path
            id="path3026"
            d="m263.41 226.14v-171.3h-201.55l-20.805 12.3v247h212.89v-22.035h30.598c-0.001 0-21.134-16.965-21.134-65.965zm-14-37h-36.45v-39h36.441v38.999zm-89.19-84v39h-40.75v-39h40.75zm6 0h40.75v39h-40.75v-39zm-90.356 0h37.605v39h-37.611v-39zm0 45.001h37.605v39h-37.611v-38.999zm0 44.998h37.605v31.008c0 2.792 0.059 5.451 0.166 7.994h-37.781v-39.002zm43.606 31.008v-31.008h40.75v31.008c0 2.792 0.059 5.451 0.166 7.994h-40.745c-0.111-2.53-0.171-5.187-0.171-7.994zm0-37.008v-39h40.75v38.999h-40.75zm46.75-38.998h40.75v38.999h-40.75v-38.999zm83.191-6h-36.441v-39h36.441v39zm-135.41 96c1.581 19.828 6.476 31.323 11.354 37.963h-39.126c-0.952-0.84-2.545-2.62-4.217-6.1-2.521-5.24-5.467-14.92-6.04-31.86h38.027zm19.349 37.963c-4.706-4.322-11.4-14.504-13.334-37.963h40.735c1.581 19.828 6.476 31.323 11.354 37.963h-38.755zm46.75 0c-4.706-4.322-11.4-14.504-13.334-37.963h40.735c1.581 19.828 6.476 31.323 11.354 37.963h-38.755zm-13.707-43.963c-0.11-2.53-0.171-5.188-0.171-7.994v-31.008h40.75v31.008c0 2.792 0.059 5.451 0.166 7.994h-40.745zm46.579-7.994v-31.008h36.441v37.006c0 0.672 0.011 1.332 0.018 1.996h-36.288c-0.111-2.53-0.171-5.187-0.171-7.994zm26.976 73.992h-184.9v-225.01l6.805-4.022v163.04c0 54 21.133 57.957 21.133 57.957h156.95v8.035zm14-22.035h-27.099c-4.706-4.322-11.4-14.504-13.334-37.963h36.072c0.635 14.755 3.059 27.463 7.253 37.963h-2.892z"
          />
          <metadata>
            <rdf:RDF
              ><cc:Work
                ><dc:format>image/svg+xml</dc:format
                ><dc:type
                  rdf:resource="http://purl.org/dc/dcmitype/StillImage"
                /><cc:license
                  rdf:resource="http://creativecommons.org/licenses/publicdomain/"
                /><dc:publisher
                  ><cc:Agent rdf:about="http://openclipart.org/"
                    ><dc:title>Openclipart</dc:title></cc:Agent
                  ></dc:publisher
                ></cc:Work
              ><cc:License
                rdf:about="http://creativecommons.org/licenses/publicdomain/"
                ><cc:permits
                  rdf:resource="http://creativecommons.org/ns#Reproduction" /><cc:permits
                  rdf:resource="http://creativecommons.org/ns#Distribution" /><cc:permits
                  rdf:resource="http://creativecommons.org/ns#DerivativeWorks" /></cc:License
            ></rdf:RDF>
          </metadata>
        </svg>
      </button>

      <a
        href="https://www.instagram.com/nonunonu_/"
        target="_blank"
        rel="noopener noreferrer"
      >
        <button>
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
            <path
              d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"
            />
          </svg>
        </button>
      </a>
    </div>
  </div>
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
      showGigs: false,
      gigs: [
        // {
        //   venue: "Template of Art and Music, London",
        //   date: "RESCHEDULED - TBA",
        //   link: "http://www.tam.tv/",
        // },
        // {
        //   venue: "Fuel, Manchester",
        //   date: "13/03/22",
        //   link: "https://www.facebook.com/fuelcafebar/",
        // },
        // {
        //   venue: "Matt and Phreds, Manchester",
        //   date: "23/03/22",
        //   link: "https://mattandphreds.com/march-2022/nonunonu",
        // },
        // {
        //   venue: "Revoler, Liverpool",
        //   date: "25/04/22",
        //   link:
        //     "https://revolverliverpool.co.uk/?fbclid=IwAR0X9l1LeW6xExndfpGQRbRgWlIh7D4b6e3u0pii-EYDgqHnR1OW6ikTr-U",
        // },
        {
          venue: "Esk Fest",
          date: "2022-07-08T19:00:00.000",
          link: "https://www.eskfest.com/",
        },
        {
          venue: "Manchester Jazz Festival",
          date: "2022-05-24",
          link: "https://manchesterjazz.com/",
        },
        {
          venue: "Elder Beer Café, Newcastle",
          date: "2022-07-21T19:00:00.000",
          link: "https://www.instagram.com/elder_beercafe/",
        },
        {
          venue: "Ramona",
          date: "2022-06-15T19:00:00.000",
          link: "https://www.takemetoramona.com/",
        },
        {
          venue: "Frederik's, Liverpool",
          date: "2022-07-05T21:00:00.000",
          link: "https://frederikshopestreet.com/",
        },
      ],
    };
  },
  methods: {
    animate() {},
  },
};
</script>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  padding: 0;
  height: 100vh;
  width: 99vw;
}

/* #app {
  width: 99vh;
  overflow-x: hidden;
} */

.buttons svg {
  fill: darkgreen;
  height: 2.5rem;
}

.gig-listings {
  position: absolute;
  top: 0;
}

.buttons {
  display: flex;
  align-items: center;
  align-self: center;
  justify-content: space-evenly;
  width: 100%;
  position: absolute;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  bottom: 1rem;
  text-align: center;
}
button {
  height: 5rem;
  width: 5rem;
  border: 2px darkgreen;
  border-radius: 1rem;
  opacity: 0.85;
  font-family: Courier;
  box-shadow: 1px 7px 5px -5px;
}

@media (min-width: 500px) {
  .buttons {
    bottom: 6rem;
  }
}

/* #
  Desktop
  only
  screen
  and
  (min-width: 992px)
  #
  Huge
  only
  screen
  and */
(min-width: 1280px)
  @keyframes
  rotate {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

.gradient {
  --size: 300px;
  position: relative;
  top: -20rem;
  width: var(--size);
  height: var(--size);
  filter: blur(calc(var(--size) / 6));
  background-image: linear-gradient(
    rgba(248, 232, 89, 0.85),
    rgb(223, 166, 32)
  );
  animation: rotate 20s cubic-bezier(0.8, 0.2, 0.2, 0.8) alternate infinite;
}

.shape {
  border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
}

body {
  background-color: rgb(0, 170, 255, 1);
  position: absolute;
  inset: 0;
  display: flex;
  /* place-content: center; */
  align-items: center;
  overflow: hidden;
}
</style>
