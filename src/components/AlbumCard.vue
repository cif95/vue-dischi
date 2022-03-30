<template>
  <div class="col-6 col-md-4 col-lg-2">
    <div class="my-album-card">
      <img
        class="img-fluid"
        src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
        alt=""
      />
      <h5 class="my-card-title text-white text-uppercase pt-3 fw-bold">
        New jersey
      </h5>
      <p class="my-card-text">Bon Jovi</p>
      <span class="my-card-text">1988</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "AlbumCard",
};
</script>

<style scoped lang="scss">
@import "../assets/scss/partials/_variables.scss";
div.my-album-card {
  color: grey;
  padding: 1.2rem 1.2rem 3.4rem;
  text-align: center;
  background-color: $lightGray;
  p {
    margin-bottom: 0;
  }
}
</style>
