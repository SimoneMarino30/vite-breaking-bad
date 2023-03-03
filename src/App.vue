<script>
import AppMain from "./components/AppMain.vue";
import AppSelect from "./components/AppSelect.vue";
import axios from "axios";
import { store } from "./data/store";

export default {
  data() {
    return {
      store,
      endpoint: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0",
      title: "Yu-Gi-Oh Api",
    };
  },
  components: { AppMain, AppSelect },

  methods: {
    fetchSelectedType() {
      console.log("####");
    },
  },

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
  <header class="container-fluid">
    <div class="container">
      <h1>{{ title }}</h1>
    </div>
  </header>

  <AppSelect @selectType="fetchSelectedType" />
  <!-- big card -->
  <AppMain />
</template>

<style lang="scss">
@use "./scss/style.scss";
</style>
