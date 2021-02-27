<template>
  <div class="container">
    <b-card-group columns class="border-variant">
      <div v-for="person in character" :key="person.id">
        <b-card
          :title="person.name"
          :img-src="person.image"
          img-alt="Image"
          img-top
          class="card"
        >
          <nuxt-link :to="`character/${person.id}`">
            <b-button variant="outline-primary">Ver mas</b-button></nuxt-link
          >
        </b-card>
      </div>
    </b-card-group>
  </div>
</template>

<script>
import axios from "axios";
import env from "../api/rickAndMorty.js";
export default {
  name: "Principal",
  data() {
    return {
      character: [],
    };
  },
  async created() {
    let info = await axios.get(`${env.endPoint}/character/?page=14`);
    this.character = info.data.results;
  },
};
</script>

<style lang="css" scoped>
.border {
  border: 2px solid green;
}
</style>
