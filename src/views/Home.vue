<template>
  <div class="container-fluid mt-5 m-auto px-lg-2">
    <div
      class="
        row
        m-auto
        py-2
        gap-2
        d-flex
        justify-content-sm-evenly
        justify-content-md-evenly
        justify-content-lg-evenly
        justify-content-between
      "
    >
      <Card v-for="(card, index) in dataCard" :key="index" :data="card" />
      <!-- <Pagination v-if="totalPages" :pages="totalPages" /> -->
    </div>
  </div>
</template>

<script>
import Card from "../components/Card.vue";
// import Pagination from "../components/Pagination.vue";
import axios from "axios";

export default {
  components: { Card },
  name: "Home",
  data() {
    return {
      dataCard: null,
      totalPages: null,
    };
  },
  async beforeCreate() {
    const response = await axios.get(
      "http://www.omdbapi.com/?apikey=96352600&s=harry"
    );
    this.dataCard = response.data.Search;
    const totalResults = response.data.totalResults;
    this.totalPages = Math.floor(totalResults / 10);
  },
  methods: {
    async searchMovie() {
      const keyword = this.keyword;
      const response = await axios({
        method: "get",
        url: `http://www.omdbapi.com/?apikey=96352600&s=${keyword}`,
      });
      this.dataCard = response.data.Search;
    },
  },
};
</script>


