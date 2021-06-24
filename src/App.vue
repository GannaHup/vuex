<template>
  <Navigation />
  <router-view />
</template>

<script>
import Navigation from "./components/Navigation.vue";

export default {
  name: "App",
  components: {
    Navigation,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  background-color: rgb(167, 167, 167);
}
</style>
