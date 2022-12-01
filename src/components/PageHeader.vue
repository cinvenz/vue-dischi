<template>
  <header>
    <label for="select-genres">
      <select id="select-genres" v-model="genreFilter" name="genre" @change="genreChange">
        <option value="all">All genres</option>
        <option v-for="genre in genresList" :key="genre" :value="genre">
          {{ genre }}
        </option>
      </select>
    </label>
  </header>
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
