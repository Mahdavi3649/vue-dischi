<template>
  <header class="d-flex justify-content-between align-items-center">
    <div class="d-flex">
      <img src="@/assets/img/logo.png" alt="" />
    </div>

    <SearchBox v-model="searchText" @formSubmit="search"></SearchBox>
  </header>
</template>

<script>
import SearchBox from "@/components/SearchBox.vue";
import state from "@/state.js";
export default {
  name: "HeaderComponent",
  components: {
    SearchBox,
  },
  data() {
    return {
      searchText: "",
    };
  },
  methods: {
    search() {
      console.log("searching ...");
      console.log(this.searchText);
      state.searchText = this.searchText;
      console.log(state);
    },
  },
};
</script>

<style scoped lang="scss">
header {
  background-color: $bg-light;

  img {
    width: 45px;
    margin: 0.8rem 1rem;
  }
  form {
    height: 35px;
    width: 20rem;
    margin: 0.8rem 1rem;
  }
}
</style>
