<template>
  <v-card elevation="0" color="transparent" width="" class="pa-0">
    <v-card-text class="text-center pa-0">
      <v-row class="space-around" no-gutters>
        <v-col cols="">
          <v-icon
            style="border-radius: 30px"
            class="pa-2"
            :class="color"
            color="white"
            :size="iconSize"
            >{{ icon }}</v-icon
          >
        </v-col>
      </v-row>
    </v-card-text>
    <v-card-actions class="pa-0 pt-2 justify-center">
      <div class="text-body-2 white--text">
        <span class="title-font" :style="{ fontSize: textFontSize + 'px' }">
          {{ text }}
        </span>
      </div>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: "CallAction",
  props: ["textFontSize", "iconFontSize", "type"],
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
    text() {
      if (this.type == "accept") {
        return "Répondre";
      } else {
        return "Refuser";
      }
    },
  },
};
</script>

