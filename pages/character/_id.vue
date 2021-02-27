<template>
  <div class="lala">
    <img :src="char.image" :alt="char.name" />
    <div class="description">
      <h1 class="title spacing">{{ char.name }}</h1>
      <h4 class="title-h4 spacing">Specie: {{ char.species }}</h4>
      <h6 class="title-h6 spacing">Status: {{ char.status }}</h6>
      <!-- <h6 class="title-h6 spacing">Status: {{ thischar.location.name }}</h6> -->
      <nuxt-link to="/">
        <b-button variant="outline-danger ml-4">Go back</b-button></nuxt-link
      >
    </div>
  </div>
</template>

<script>
import env from "../../api/rickAndMorty.js";
import axios from "axios";

export default {
  name: "character",
  layout: "default",

  data() {
    return {
      char: {},
    };
  },

  async created() {
    let characterId = await axios.get(
      `${env.endPoint}/character/${this.$route.params.id}`
    );
    this.char = characterId.data;
    console.log("laaaaaaaaaaaaaa", this.char.location.name);
  },
};
</script>

<style lang = 'css' scoped>
.lala {
  display: flex;
  height: 100vh;
  mix-blend-mode: 87%;
  color: #fff;
}

.spacing {
  margin: 2rem;
}

.title {
  font-size: 100px;
}

.title-h4 {
  font-size: 50px;
}

.title-h6 {
  font-size: 32px;
}
img {
  width: 50%;
  height: 100%;
}
</style>