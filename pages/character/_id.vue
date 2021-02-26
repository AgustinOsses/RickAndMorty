<template>
  <div>
    <h1>{{ char.name }}</h1>
    <img :src="char.image" alt="asd" />
    <nuxt-link to="/">
      <b-button variant="outline-primary">Volver al inicio</b-button></nuxt-link
    >
  </div>
</template>

<script>
import env from "../../api/rickAndMorty.js";
import axios from "axios";

export default {
  name: "character",

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

    //     this.char = characterId;
    //     console.log(this.char);
  },
};
</script>

<style lang = 'css' scoped>
</style>