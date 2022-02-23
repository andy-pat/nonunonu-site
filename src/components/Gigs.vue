<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <ul>
        <li v-for="(gig, index) of gigs" :key="index">
          <div>
            <p>
              <strong> {{ gig.venue }}</strong> - <i>{{ gig.date }}</i>
              <a
                v-if="gig.link"
                :href="gig.link"
                style="padding:5px"
                target="_blank"
                ><i class="fas fa-external-link-alt"></i
              ></a>
            </p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: ["gigs"],
  data() {
    return {};
  },
  methods: {
    closeModal() {
      this.$emit("closeModal");
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
</style>
