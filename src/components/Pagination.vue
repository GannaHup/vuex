<template>
  <h2>{{ count }}</h2>
  <nav class="d-flex justify-content-center align-items-center mt-5 mb-4">
    <ul class="pagination m-0">
      <li v-if="pageNow === 0" class="page-item disabled">
        <a class="page-link" href="#" tabindex="-1" aria-disabled="true"
          >Previous</a
        >
      </li>
      <li v-else-if="pageNow > 0" class="page-item">
        <button class="page-link" @click="prevPages">Previous</button>
      </li>
      <li v-for="count in 3" :key="count" class="page-item">
        <button v-if="pageNow + count === pageActive" class="page-link active">
          {{ pageNow + count }}
        </button>
        <button v-else-if="pageNow + count !== pageActive" class="page-link">
          {{ pageNow + count }}
        </button>
      </li>
      <li class="page-item">
        <button class="page-link" @click="nextPages">Next</button>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Pagination",
  props: ["pages"],
  data() {
    return {
      pageNow: 0,
      pageActive: 1,
    };
  },
  created() {},
  methods: {
    nextPages() {
      this.pageNow += 1;
    },
    prevPages() {
      if (this.pageNow > 0) {
        this.pageNow -= 1;
      }
    },
  },
};
</script>

<style>
li.page-item .page-link {
  color: #07b33b;
}

li.page-item.active .page-link {
  background-color: #07b33b;
  border: 1px solid #07b33b;
}
</style>