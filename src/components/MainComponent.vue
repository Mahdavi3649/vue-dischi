<template>
  <main>
    <section v-if="!loading">
      <div class="container">
        <div class="row p-5">
          <ItemComponent
            :album="album"
            v-for="(album, index) in musics"
            :key="index"
          />
        </div>
      </div>
    </section>
    <div
      class="d-flex min-vh-100 align-items-center justify-content-center"
      v-else
    >
      <h3>loading...</h3>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import ItemComponent from "@/components/ItemComponent.vue";

export default {
  name: "MainComponent",
  components: {
    ItemComponent,
  },

  data() {
    return {
      link: "https://flynn.boolean.careers/exercises/api/array/music",
      musics: null,
      loading: true,
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
        this.loading = false;
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
}
</style>
