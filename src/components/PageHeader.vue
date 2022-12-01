<template>
  <div class="container-header py-2 ps-3">
    <img class="img-fluid" src="../../public/logo-small.svg" alt="" />

    <label for="select-genres">
      <select id="select-genres" v-model="genreFilter" name="genre" @change="genreChange">
        <option value="all">all genres</option>
        <option v-for="genre in genresList" :key="genre" value="genre">
          {{ genre }}
        </option>
      </select>
    </label>
  </div>
</template>

<script>
export default {
  name: "PageHeader",
  props: {
    genresList: Array,
  },
  data() {
    return {
      genreFilter: "all",
    };
  },
  methods: {
    genreChange() {
      this.$emit("changedGenre", this.genreFilter);
    },
  },
};
</script>

<style lang="scss" scoped>
.container-header {
  background-color: #2e3a46;
}
img {
  width: 2rem;
}
#select-genres {
  width: 5rem;
}
</style>
