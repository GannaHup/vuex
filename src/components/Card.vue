<template>
  <div
    class="
      card
      position-relative
      overflow-hidden
      col-10
      offset-1
      col-sm-5 col-md-3 col-xl-2
      offset-sm-0
      p-0
    "
  >
    <img v-bind:src="poster" class="img-fluid image-movie" />
    <div class="card-body position-absolute end-0 bottom-0 start-0">
      <span class="card-title fs-6 text text-light">{{ title }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["data"],
  data() {
    return {
      title: this.data.Title,
      poster: this.data.Poster,
      year: this.data.Year,
    };
  },
};
</script>
<style scoped>
.card-body {
  text-align: center;
  background: linear-gradient(
    0deg,
    rgba(0, 0, 0, 1) 26%,
    rgba(255, 255, 255, 0) 100%
  );
}
</style>