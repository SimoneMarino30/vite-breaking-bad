<script>
import axios from "axios";
import CharacterCard from "./CharacterCard.vue";

export default {
  data() {
    return {
      cards_list: [],
    };
  },

  components: { CharacterCard },

  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0")
      .then((resp) => {
        console.log(resp);
        this.cards_list = resp.data.data;
      });
  },
};
</script>

<template>
  <div class="big-card-border m-2">Found TOT cards</div>
  <div class="container">
    <div class="row row-cols-5">
      <CharacterCard
        v-for="card in cards_list"
        :pic="card.card_images[0].image_url"
        :name="card.name"
        :archetype="card.archetype"
        :attribute="card.attribute"
      />
      <!-- <img :src="" alt="" class="img-fluid" />
        <h5>{{  }}</h5>
        <p>{{  }}</p>
        <p>{{  }}</p> -->
    </div>
  </div>
</template>

<style lang="scss" scoped>
.row {
  border: 3px dashed blue;
}
</style>
