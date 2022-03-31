<template>
  <main class="p-4">
    <div class="container">
      <div
        class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 p-5 gx-5"
      >
        <AlbumCard
          :albumObj="album"
          v-for="(album, index) in albums"
          :key="index"
        />
      </div>
    </div>
  </main>
</template>

<script>
import AlbumCard from "./AlbumCard.vue";
import axios from "axios";

export default {
  name: "IndexAlbums",
  data() {
    return {
      albums: [],
    };
  },
  components: {
    AlbumCard,
  },
  methods: {
    getAlbums() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          // console.log(result.data.response);
          this.albums = result.data.response;
          console.log(this.albums);
        })
        .catch((error) => console.error(error));
    },
  },
  created() {
    this.getAlbums();
  },
};
</script>

<style scoped lang="scss">
@import "../assets/scss/partials/_variables.scss";
main {
  background-color: $darkBlueGray;
}
</style>
