<template>
  <div class="col-2-5">
    <img :src="album.poster" />
    <h3 class="fs-6 text-center text-white fw-bold mt-3 text-uppercase">
      {{ album.title }}
    </h3>
    <div class="caption mt-3">{{ album.author }}</div>
    <div class="caption">{{ album.year }}</div>
  </div>
</template>

<script>
export default {
  name: "ItemComponent",
  props: {
    album: Object,
  },
};
</script>

<style lang="scss" scoped>
img {
  max-width: 100%;
}
.col-2-5 {
  flex: 0 0 auto;
  width: 18%;
  margin: 1%;
  padding: 25px;
  background-color: $bg-light;
}

.caption {
  text-align: center;
  font-size: 14px;
  color: #807f7f;
  font-weight: 500;
}
</style>
