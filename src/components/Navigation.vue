<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid d-flex align-items-center">
      <h4 class="m-0 me-2">
        <router-link to="/" class="nav-brand text-decoration-none text-light"
          >VueMovies</router-link
        >
      </h4>
      <!-- Button Toggle -->
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <router-link to="/" class="nav-link">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/about" class="nav-link">About</router-link>
          </li>
        </ul>
        <form
          class="d-flex align-items-center"
          @submit="(event) => showInput(event)"
        >
          <input
            class="form-control me-2"
            style="height: 30px"
            type="search"
            placeholder="Search"
            aria-label="Search"
            v-model="keyword"
          />
          <button
            class="btn btn-outline-success d-flex align-items-center"
            style="height: 30px"
            type="submit"
          >
            Search
          </button>
        </form>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navigation",
  data() {
    return {
      keyword: "",
    };
  },
  methods: {
    showInput(event) {
      event.preventDefault();

      const { keyword } = this;

      console.log(keyword);
    },
  },
};
</script>
