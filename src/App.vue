<script>
import AppMain from "./components/AppMain.vue";
import axios from "axios";
import { store } from "./data/store";

export default {
  data() {
    return {
      store,
      title: "Yu-Gi-Oh Api",
    };
  },
  components: { AppMain },

  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0")
      .then((resp) => {
        console.log(resp);
        store.cards_list = resp.data.data;
      });
  },
};
</script>

<template>
  <!-- header -->
  <!-- <header class="container-fluid"> -->
  <!-- <div class="container"> -->
  <!-- <h1>{{ title }}</h1> -->
  <!-- </div> -->
  <!-- </header> -->
  <!-- big card -->
  <AppMain />
</template>

<style lang="scss">
@use "./scss/style.scss";
</style>
