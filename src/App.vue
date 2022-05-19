<template>
  <div id="app">
    <AppHeader />
    <main>
      <AppAlbum />
    </main>
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppAlbum from "./components/AppAlbum.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    AppAlbum,
  },
};
</script>

<style lang="scss">
@import "./style/common.scss";
</style>
