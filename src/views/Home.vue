<template>
  <v-container class="" fluid>
    <v-row justify="center">
      <div class="">
        <Phone />
      </div>
      <div class="pa-2"></div>
      <div>
        <Kiosk />
      </div>
      <div class="pa-2"></div>
      <div class="">
        <Phone />
      </div>
      <!-- <v-col class="red" cols="3">
        <Phone />
      </v-col>
      <v-col class="green" cols="6"></v-col>
      <v-col class="red" cols="3">
        <Phone />
      </v-col> -->
    </v-row>
  </v-container>
</template>


<script>
/* eslint-disable vue/no-unused-components */
import Phone from "../components/Phone";
import Kiosk from "../components/Kiosk";

export default {
  name: "Home",

  components: {
    Kiosk,
    Phone
  },
};
</script>
