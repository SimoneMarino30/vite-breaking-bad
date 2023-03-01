<script>
import CharacterCard from "./CharacterCard.vue";
import { store } from "../data/store";

export default {
  data() {
    return {
      store,
    };
  },
  components: { CharacterCard },
};
</script>

<template>
  <div class="big-card-border m-2">Found TOT cards</div>
  <div class="container">
    <div class="row row-cols-5">
      <CharacterCard
        v-for="card in store.cards_list"
        :key="card.id"
        :pic="card.card_images[0].image_url"
        :name="card.name"
        :archetype="card.archetype"
        :attribute="card.attribute"
      />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.row {
  //   border: 3px dashed blue;
}
</style>
