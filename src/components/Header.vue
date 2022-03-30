<template>
  <header>
    <img src="../assets/img/spotify-logo.png" alt="spotify-logo" />
  </header>
</template>

<script>
export default {
  name: "IndexHeader",
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
}
</style>
