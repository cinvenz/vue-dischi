<template>
  <div class="col">
    <div class="contents text-center">
      <img :src="imgUrl" :alt="name" class="img-fluid" />
      <h3 class="name">
        {{ name }}
      </h3>
      <div class="origin">
        {{ genre }}
      </div>
      <div class="species">
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
    genre: String,
    anno: Number,
  },
};
</script>

<style lang="scss" scoped></style>
