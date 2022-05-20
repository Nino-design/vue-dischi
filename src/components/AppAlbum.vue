<template>
  <section>
  <div class="choose">
  <select class="form-select form-select-sm container" aria-label=".form-select-sm example">
  <option selected>Choose the genre</option>
  <option value="1">Rock</option>
  <option value="2">Pop</option>
  <option value="3">Jazz</option>
  <option value="3">Metal</option>
</select>
  </div>
    <div
      class="
        container
        d-flex
        justify-content-center
        align-items-center
        mt-5
        mb-5
      "
    >
      <div class="row row-cols-5">
        <AppAlbumCard
          v-for="(element, index) in albums"
          :key="index"
          :albumCardObject="element"
        />
      </div>
    </div>
  </section>
</template>

<script>
import AppAlbumCard from "./AppAlbumCard.vue";
import axios from "axios";
export default {
  name: "AppAlbum",
  components: {
    AppAlbumCard,
  },
  data() {
    return {
      albums: [],
    };
  },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.albums = resp.data.response;
      });
  },
};
</script>



<style lang="scss" scoped>
section {
  height: 100%;
  overflow-y: hidden;
  background-color: rgba(30, 45, 59, 255);
}
</style>