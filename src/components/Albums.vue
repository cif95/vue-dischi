<template>
  <main>
    <div class="container-fluid">
      <div class="row p-5">
        <AlbumCard />
      </div>
    </div>
  </main>
</template>

<script>
import AlbumCard from "./AlbumCard.vue";

export default {
  name: "IndexAlbums",
  components: {
    AlbumCard,
  },
};
</script>

<style scoped lang="scss">
@import "../assets/scss/partials/_variables.scss";
div.container-fluid {
  height: 92vh;
  background-color: $darkBlueGray;
}
</style>
