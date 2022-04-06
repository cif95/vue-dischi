<template>
  <header class="d-flex align-items-center justify-content-between">
    <img src="../assets/img/spotify-logo.png" alt="spotify-logo" />
    <select
      class="form-select me-4"
      v-model="selected"
      @change="$emit('genreSelect', selected)"
    >
      <option disabled value="">Choose a genre</option>
      <option v-for="(el, index) in genres" :key="index" :value="el">
        {{ el }}
      </option>
    </select>
  </header>
</template>

<script>
export default {
  name: "IndexHeader",
  props: ["genres"],
  data() {
    return {
      selected: "",
    };
  },
};
</script>
<style scoped lang="scss">
@import "../assets/scss/partials/_variables.scss";
header {
  height: 8vh;
  background-color: $lightGray;
  img {
    height: 65%;
    padding-left: 1.5rem;
  }
  select.form-select {
    width: 20%;
  }
}
</style>
