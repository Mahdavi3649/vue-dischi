<template>
  <main>
    <div class="container">
      <div class="row">
        <div class="col-2" v-for="(album, index) in musics" :key="index">
          <img :src="album.poster" />
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
        this.response = response.data;
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
  height: 100vh;
}
</style>
