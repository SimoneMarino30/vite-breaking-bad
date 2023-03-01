<script>
import CharacterList from "./CharacterList.vue";

export default {
  components: { CharacterList },
};
</script>

<template>
  <main class="container big-card my-5">
    <div class="divider"></div>
    <CharacterList />
  </main>
</template>

<style lang="scss" scoped>
.divider {
  height: 1rem;
}
</style>
