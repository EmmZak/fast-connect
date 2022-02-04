<template>
  <v-card elevation="0" color="transparent" width="" class="pa-0">
    <v-card-text class="text-center pa-0">
      <v-row class="space-around" no-gutters>
        <v-col cols="">
          <v-icon
            x-large
            style="border-radius: 30px"
            class="pa-2"
            :class="color"
            color="white"
            >{{ icon }}</v-icon
          >
        </v-col>
      </v-row>
    </v-card-text>
    <v-card-actions class="pa-0 justify-center">
      <div class="text-body-2 white--text">
        <span class="title-font"> Répondre </span>
      </div>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: "CallAction",
  props: ["type"],
  computed: {
    icon() {
      if (this.type == "accept") {
        return "mdi-phone";
      } else {
        return "mdi-phone-hangup";
      }
    },
    color() {
      if (this.type == "accept") {
        return "green";
      } else {
        return "red";
      }
    },
  },
};
</script>

