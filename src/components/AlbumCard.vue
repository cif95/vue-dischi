<template>
  <div class="col">
    <div class="my-album-card">
      <img class="img-fluid" :src="albumObj.poster" :alt="albumObj.title" />
      <h5 class="my-card-title">
        {{ albumObj.title }}
      </h5>
      <p class="my-card-text">{{ albumObj.author }}</p>
      <span class="my-card-text">{{ albumObj.year }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "AlbumCard",
  props: {
    albumObj: Object,
  },
};
</script>

<style scoped lang="scss">
@import "../assets/scss/partials/_variables.scss";
div.my-album-card {
  @include albumCard;
}
</style>
