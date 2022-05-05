<template>
  <header>
    <div class="logo">
      <img src="@/assets/img/logo.png" alt="" />
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
};
</script>

<style scoped lang="scss">
header {
  background-color: #2e3a46;

  img {
    width: 45px;
    margin: 0.6rem;
    padding: 0.3rem 0;
  }
}
</style>
