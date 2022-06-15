<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <ul>
        <li v-for="(gig, index) of order" :key="index">
          <p>
            <strong>
              {{ gig.venue }}
              <a
                v-if="gig.link"
                :href="gig.link"
                style="padding: 5px"
                target="_blank"
                title="click for more info"
                ><i class="fas fa-external-link-alt"></i></a
            ></strong>
            <br />
            <small>
              {{ displayDate(gig.date) }}
            </small>
            <br />
            <i style="font-size: 10px">({{ formatDate(gig.date) }})</i>
          </p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import * as dayjs from "dayjs";
var relativeTime = require("dayjs/plugin/relativeTime");
var isToday = require("dayjs/plugin/isToday");

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
      // dayjs.extend(isToday);
      // if (dayjs(date).isToday()) {
      //   return "Today";
      // } else {
      dayjs.extend(relativeTime);
      return (
        dayjs(date, "YYYY-MM-DD")
          // add(1, "d").
          .fromNow()
      );
      // }
    },
    displayDate(date) {
      return dayjs(date).format("HH:mm dddd, MMMM D, YYYY");
    },
  },
  computed: {
    order() {
      const upcomingDates = this.gigs.filter((gig) => {
        const today = new Date();
        const dateToCheck = new Date(gig.date);
        if (dateToCheck.setHours(0, 0, 0, 0) >= today.setHours(0, 0, 0, 0)) {
          return gig;
        }
        return false;
      });
      return upcomingDates.sort((a, b) => {
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
  position: fixed;
  /* top: 0; */
  /* left: 0; */
  transform: translate(25%, 25%);
  padding: 1rem;
  width: fit-content;

  z-index: 1;
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
