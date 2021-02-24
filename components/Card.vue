<template>
  <div class="container">
    <b-card-group columns>
      <div v-for="person in character" :key="person.id">
        <b-card
          :title="person.name"
          :img-src="person.image"
          img-alt="Image"
          img-top
          class="card"
        >
          <b-card-text> Species: {{ person.species }} </b-card-text>
          <b-card-text> Status: {{ person.status }} </b-card-text>
        </b-card>
      </div>
    </b-card-group>
  </div>
</template>

<script>
import axios from "axios";
import env from "../config/.env";
export default {
  name: "Principal",
  data() {
    return {
      character: []
    };
  },
  created() {
    axios.get(`${env.endPoint}/character/?page=3`).then(info => {
      this.character = info.data.results;
      console.log("laaaaaaaaaaaaaaaaaaaa", this.character);
    });
  }
};
</script>

<style lang="css" scoped></style>
