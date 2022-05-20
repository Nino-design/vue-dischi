<template>
  <div class="album-wrapper m-3 text-center">
    <img class="pt-3" :src="albumCardObject.poster" alt="" />
    <h5 class="fw-bold mt-2 mb-2">{{ albumCardObject.title }}</h5>
    <p class="m-0">{{ albumCardObject.author }}</p>
    <span>{{ albumCardObject.year }}</span>
  </div>
</template>

<script>
export default {
  name: "AppAlbumCard",
  props: {
    albumCardObject: Object,
  },
};
</script>

<style lang="scss" scoped>
.album-wrapper {
  width: calc(100% / 6);
  background-color: rgba(46, 58, 70, 255);
  color: white;

  p,
  span {
    color: #626d77;
  }
}
</style>