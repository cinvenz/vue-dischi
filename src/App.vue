<template>
  <div>
    <PageHeader :genres-list="genresList" @changedGenre="genreChange" />
    <PageMain :genre-filter="genreFilter" @genresReady="getGenresList" />
  </div>
</template>

<script>
// TODO: import bootstrap script
import PageHeader from "@/components/PageHeader.vue";
import PageMain from "@/components/PageMain.vue";

export default {
  components: {
    PageHeader,
    PageMain,
  },
  data() {
    return {
      genresList: [],
      genreFilter: "all",
    };
  },
  methods: {
    getGenresList(genresList) {
      this.genresList = genresList;
    },
    genreChange(genreFilter) {
      this.genreFilter = genreFilter;
    },
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import url("https://fonts.googleapis.com/css2?family=Lato&display=swap");
body {
  font-family: "Lato", sans-serif;
  font-size: 0.8rem;
}
</style>
