<script>
import AppMain from "./components/AppMain.vue";

export default {
  data() {
    return {
      title: "Yu-Gi-Oh Api",
    };
  },
  components: { AppMain },
};
</script>

<template>
  <!-- header -->
  <header class="container-fluid">
    <div class="container">
      <h1>{{ title }}</h1>
    </div>
  </header>
  <!-- big card -->
  <AppMain />

  <!-- <div class="divider"></div>
    <div class="big-card-border m-2">Found TOT cards</div>
    <div class="container">
      <div class="card-box"></div>
    </div> -->
</template>

<style lang="scss">
@use "./scss/style.scss";
</style>
