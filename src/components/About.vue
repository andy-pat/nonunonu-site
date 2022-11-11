<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <h3>Matt & Phreds Testimonial</h3>
      <p>
        NONUNONU masterfully blend jazz, hip-hop, and funk in their own unique
        and highly authentic style, boasting an impressive number of original
        numbers as well as their exciting arrangements of standards and classics
        from the genres.
      </p>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.modal {
  background: white;
  border-radius: 10px;
  transform: translate(0%, 39%);
  padding: 1rem;
  width: -moz-fit-content;
  z-index: 1;
  margin: 1rem;
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
