<template>
  <div class="choose">
    <select
      class="form-select form-select-sm container text-center fs-5"
      aria-label=".form-select-sm example"
      v-model="chooseGenre"
      @change="$emit('genreSelected', chooseGenre)"
    >
      <option selected>Choose the genre</option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
    name: "AppSelectGenre",

     data() {
    return {
      chooseGenre: "",
    };
  },
};

</script>

<style lang="scss" scoped>


</style>