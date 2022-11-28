<template>
  <div class="col">
    <div class="contents text-center container-card p-3">
      <img :src="imgUrl" :alt="name" class="img-fluid" />
      <h2 class="name fw-bold text-uppercase pt-3 pb-2">
        {{ name }}
      </h2>
      <div class="author">
        {{ author }}
      </div>
      <div class="anno">
        {{ anno }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardDisc",
  props: {
    imgUrl: String,
    name: String,
    author: String,
    anno: Number,
  },
};
</script>

<style lang="scss" scoped>
.container-card {
  background-color: #2e3a46;
  color: white;
  height: 18rem;
}
h2 {
  font-size: 1rem;
}
.author {
  color: gray;
}
.anno {
  color: gray;
}
</style>
