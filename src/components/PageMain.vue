<template>
  <div class="container-main">
    <div v-if="arrDisc" class="row row-cols-5 g-4 container-cards py-5">
      <CardDisc v-for="objMovie in arrDiscsFiltered" :key="objMovie.title" :movie-info="objMovie" />
    </div>
    <div v-else>Loading ...</div>
  </div>
</template>

<script>
import axios from "axios";
import CardDisc from "@/components/CardDisc.vue";

export default {
  name: "PageMain",
  components: {
    CardDisc,
  },
  props: {
    genreFilter: String,
  },
  data() {
    return {
      urlApi: "https://flynn.boolean.careers/exercises/api/array/music",
      arrDisc: null,
    };
  },
  computed: {
    arrGenres() {
      const arrGenres = [];
      if (this.arrDisc) {
        this.arrDisc.forEach((objDisc) => {
          if (!arrGenres.includes(objDisc.genre)) {
            arrGenres.push(objDisc.genre);
          }
        });
      }
      return arrGenres;
    },
    arrDiscsFiltered() {
      if (this.genreFilter === "all") {
        return this.arrDisc;
      }
      return this.arrDisc.filter((objDisc) => objDisc.genre === this.genreFilter);
    },
  },
  watch: {
    arrGenres(newValue) {
      console.log(newValue);
      this.$emit("genresReady", newValue);
    },
  },
  created() {
    axios.get(this.urlApi).then((axiosResponse) => {
      console.log(axiosResponse);
      this.arrDisc = axiosResponse.data.response;
    });
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.container-main {
  background-color: #1e2d3b;
}
.container-cards {
  max-width: 900px;
  display: flex;
  margin: auto;
}
</style>
