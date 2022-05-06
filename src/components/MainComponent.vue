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
      <Loader />
    </div>
  </main>
</template>

<script>
import axios from "axios";
import ItemComponent from "@/components/ItemComponent.vue";
import Loader from "@/components/LoaderComponent.vue";

export default {
  name: "MainComponent",
  components: {
    ItemComponent,
    Loader,
  },

  data() {
    return {
      API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
      musics: null,
      loading: true,
      error: null,
    };
  },

  methods: {
    callApi() {
      axios
        .get(this.API_URL)
        .then((response) => {
          //console.log(response);
          this.musics = response.data.response;
          this.loading = false;
        })
        .catch((error) => {
          console.log(error);
          this.error = `Sorry, you have the problem error! ${error}`;
        });
    },
  },

  mounted() {
    this.callApi();
  },
};
</script>

<style scoped lang="scss">
main {
  background-color: $bg-dark;
}
</style>
