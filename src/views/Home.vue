<template>
  <v-container class="" fluid>
    <v-row
      style="background-color: #00b8ac; padding-bottom: 100px"
      justify="center"
      class="pa-10"
    >
      <div>
        <div class="text-lg-h2 text-md-h3 text-sm-body-h4 text-h5">
          <div class="title-font white--text">Essayez vous-mêmes</div>
        </div>
      </div>
    </v-row>

    <div style="padding: 1%"></div>

    <Simulator />
  </v-container>
</template>

<script>
/* eslint-disable vue/no-unused-components */
import Simulator from "../components/Simulator.vue";

export default {
  name: "Home",
  components: {
    Simulator,
  },
};
</script>
