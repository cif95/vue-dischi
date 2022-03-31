<template>
  <header>
    <img src="../assets/img/spotify-logo.png" alt="spotify-logo" />
    <select
      class="form-select ms-5"
      v-model="selected"
      @change="$emit('genreSelect', selected)"
    >
      <option disabled value="">Choose a genre</option>
      <option value="Jazz">Jazz</option>
      <option value="Rock">Rock</option>
      <option value="Metal">Metal</option>
      <option value="Pop">Pop</option>
      <option value="All">All</option>
    </select>
  </header>
</template>

<script>
export default {
  name: "IndexHeader",
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
  line-height: 8vh;
  background-color: $lightGray;
  img {
    height: 65%;
    padding-left: 1.5rem;
  }
  select.form-select {
    width: 20%;
    display: inline-block;
  }
}
</style>
