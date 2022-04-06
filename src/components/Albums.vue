<template>
  <main class="p-4">
    <div class="container">
      <div
        class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 row-cols-xl-5 p-5 gx-5"
      >
        <AlbumCard
          v-show="filterGenres(album)"
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
      albumsGenres: [],
    };
  },
  props: {
    selectedGenre: String,
  },
  components: {
    AlbumCard,
  },
  methods: {
    getAlbums() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          this.albums = result.data.response;
          console.log(this.albums);
          this.albums.forEach((element) => {
            if (!this.albumsGenres.includes(element.genre)) {
              this.albumsGenres.push(element.genre);
            }
          });
          this.$emit("gettedGenres", this.albumsGenres);
          console.warn(this.albumsGenres);
        })
        .catch((error) => console.error(error));
    },
    filterGenres(album) {
      if (
        this.selectedGenre == album.genre ||
        this.selectedGenre == "" ||
        this.selectedGenre == "All"
      ) {
        return true;
      }
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
  min-height: 92vh;
  background-color: $darkBlueGray;
}
</style>
