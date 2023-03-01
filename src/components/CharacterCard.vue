<script>
export default {
  data() {
    return {};
  },

  props: {
    pic: String,
    name: String,
    archetype: String,
    attribute: String,
  },
};
</script>

<template>
  <div class="card-box col text-center">
    <img :src="pic" alt="" class="img-fluid" />
    <h5>{{ name }}</h5>
    <p>{{ archetype }}</p>
    <p>{{ attribute }}</p>
  </div>
</template>

<style lang="scss" scoped>
h5 {
  color: #fff;
  text-transform: uppercase;
}

p {
  text-transform: lowercase;
}
img {
  min-height: 2rem;
}
</style>
