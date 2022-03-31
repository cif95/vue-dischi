<template>
  <div id="app">
    <Header @genreSelect="getSelectedGenre" />
    <Albums :selectedGenre="selectedGenre" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Albums from "./components/Albums.vue";

export default {
  name: "App",
  data() {
    return {
      selectedGenre: "",
    };
  },
  components: {
    Header,
    Albums,
  },
  methods: {
    getSelectedGenre(selected) {
      this.selectedGenre = selected;
      console.log(this.selectedGenre);
    },
  },
};
</script>

<style lang="scss">
@import "./assets/scss/main.scss";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
