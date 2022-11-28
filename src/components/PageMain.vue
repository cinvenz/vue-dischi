<template>
  <div class="conyainer-cards py-5">
    <div v-if="arrDisc" class="row row-cols-5 g-4">
      <CardDisc
        v-for="disc in arrDisc"
        :key="disc.title"
        :img-url="disc.poster"
        :name="disc.title"
        :author="disc.author"
        :anno="disc.year"
      />
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
  data() {
    return {
      arrDisc: null,
      urlApi: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
  created() {
    // scaricare i dati
    axios.get(this.urlApi).then((axiosResponse) => {
      console.log(axiosResponse);
      this.arrDisc = axiosResponse.data.response;
    });
  },
};
</script>

<style lang="scss" scoped>
.conyainer-cards {
  max-width: 900px;
  display: flex;
  margin: auto;
}
</style>
