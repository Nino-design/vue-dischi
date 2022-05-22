<template>
  <section>
  <AppSelectGenre @genreSelected='saveSelected($event)'/>
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
          v-for="(element, index) in filterGenre"
          :key="index"
          :albumCardObject="element"
        />
      </div>
    </div>
  </section>
</template>

<script>
import AppAlbumCard from "./AppAlbumCard.vue";
import AppSelectGenre from "./AppSelectGenre.vue";
import axios from "axios";
export default {
  name: "AppAlbum",
  components: {
    AppAlbumCard,
    AppSelectGenre,
  },
  data: function() {
    return {
      albums: [],
      selected: '',
    };
  },
    methods: {
      saveSelected: function(selectKey){
        this.selected = selectKey;
      }
    },
  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.albums = resp.data.response;
      });
  },
  computed: {
    filterGenre: function () {
      const generalParam = this.selected.toLowerCase();
      const filteredParam = this.albums.filter(element => {
        return element.genre.toLowerCase().includes(generalParam);
      });
      return filteredParam;
    },
  }
};
</script>



<style lang="scss" scoped>
section {
  height: 100vh;
  overflow-y: scroll;
  background-color: rgba(30, 45, 59, 255);
}
</style>