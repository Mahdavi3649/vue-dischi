<template>
  <header class="d-flex justify-content-between align-items-center">
    <div class="d-flex">
      <img src="@/assets/img/logo.png" alt="" />
    </div>
    <form class="d-flex">
      <input
        class="form-control me-2"
        type="search"
        placeholder="Search"
        aria-label="Search"
      />
      <button
        class="btn btn-outline-success d-flex align-items-center"
        type="submit"
      >
        <font-awesome-icon icon="fa-solid fa-magnifying-glass" />
        Search
      </button>
    </form>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
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
