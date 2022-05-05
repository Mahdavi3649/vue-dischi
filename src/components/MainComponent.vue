<template>
  <main>
    <div class="container">
      <div class="row p-5">
        <div class="col-2-5" v-for="(album, index) in musics" :key="index">
          <img :src="album.poster" />
          <h3 class="fs-6 text-center text-white fw-bold mt-3 text-uppercase">
            {{ album.title }}
          </h3>
          <div class="caption mt-3">{{ album.author }}</div>
          <div class="caption">{{ album.year }}</div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import axios from "axios";
export default {
  name: "MainComponent",

  data() {
    return {
      link: "https://flynn.boolean.careers/exercises/api/array/music",
      musics: null,
    };
  },

  methods: {
    callApi() {},
  },

  mounted() {
    console.log(axios);

    axios
      .get(this.link)
      .then((response) => {
        console.log(response);
        this.musics = response.data.response;
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<style scoped lang="scss">
main {
  background-color: #1e2d3b;
  img {
    max-width: 100%;
  }
}
.col-2-5 {
  flex: 0 0 auto;
  width: 18%;
  margin: 1%;
  padding: 25px;
  background-color: #2e3a46;
}

.caption {
  text-align: center;
  font-size: 14px;
  color: #807f7f;
  font-weight: 500;
}
</style>
