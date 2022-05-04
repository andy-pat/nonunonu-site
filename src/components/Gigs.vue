<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <ul>
        <li v-for="(gig, index) of order" :key="index">
          <div>
            <p>
              <strong> {{ gig.venue }}</strong>
              <br />
              {{ displayDate(gig.date) }}
              <br />
              <i style="font-size:10px">({{ formatDate(gig.date) }})</i>
            </p>
          </div>

          <div>
            <a
              v-if="gig.link"
              :href="gig.link"
              style="padding:5px"
              target="_blank"
              title="more info"
              ><i class="fas fa-external-link-alt"></i
            ></a>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import * as dayjs from "dayjs";
var relativeTime = require("dayjs/plugin/relativeTime");
// dayjs.extend(relativeTime);

export default {
  props: ["gigs"],
  data() {
    return {};
  },
  methods: {
    closeModal() {
      this.$emit("closeModal");
    },
    formatDate(date) {
      dayjs.extend(relativeTime);
      return dayjs(date, "YYYY-MM-DD").fromNow();
    },
    displayDate(date) {
      return dayjs(date).format("dddd, MMMM D, YYYY");
    },
  },
  computed: {
    order() {
      return this.gigs.sort((a, b) => {
        return new Date(a.date) - new Date(b.date);
      });
    },
  },
};
</script>

<style scoped>
.modal {
  background: white;
  border-radius: 10px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 1rem;
  width: fit-content;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

ul {
  padding: 0;
}

li {
  display: grid;
  grid-template-columns: 0.9fr 0.1fr;
}

.fa-external-link-alt {
  position: relative;
  display: flex;
  float: right;
}
</style>
