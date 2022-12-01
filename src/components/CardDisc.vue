<template>
  <div class="col">
    <div class="contents text-center container-card p-3 mb-1">
      <img :src="movieInfo.poster" :alt="movieInfo.title" class="img-fluid" />
      <h2 class="name fw-bold text-uppercase pt-3 pb-2">
        {{ movieInfo.title }}
      </h2>
      <div class="author">
        {{ movieInfo.author }}
      </div>
      <div class="anno">
        {{ movieInfo.year }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardMovie",
  props: {
    movieInfo: Object,
  },
};
</script>

<style lang="scss" scoped>
.container-card {
  background-color: #2e3a46;
  color: white;
  height: 17.5rem;
}
h2 {
  font-size: 1rem;
}
.author {
  color: gray;
  font-size: 1rem;
}
.anno {
  color: gray;
}
</style>
