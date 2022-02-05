<template>
  <v-row
    class="rounded-sm grey"
    justify="space-between"
    align="center"
    no-gutters
  >
    <v-col cols="2" class="text-centerr pa-0">
      <v-icon class="yellow--text" :size="iconFontSize">mdi-account-box</v-icon>
    </v-col>
    <v-col cols="9" class="pa-0">
      <v-row class="pa-0" no-gutters>
        <v-col class=" text-left" cols="12">
          <div
            class="white--text"
            :style="{ fontSize: titleFontSize + 'px' }"
          >
            Dispositif
          </div>
        </v-col>
        <v-col cols="12" class="text-left">
          <div
            class="white--text"
            :style="{ fontSize: messageFontSize + 'px' }"
          >
            {{ text }}
          </div>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "Notification",
  props: ["message"],
  computed: {
    text() {
      let str = `${new Date().toLocaleString().split(",")[1]} - ${
        this.message
      }`;
      return str;
    },
    iconFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 40;
        case "sm":
          return 45;
        case "md":
          return 40;
        case "lg":
          return 45;
        case "xl":
          return 50;
      }
      return null;
    },
    titleFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 12;
        case "sm":
          return 12;
        case "md":
          return 14;
        case "lg":
          return 16;
        case "xl":
          return 18;
      }
      return null;
    },
    messageFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 8;
        case "sm":
          return 9;
        case "md":
          return 9;
        case "lg":
          return 10;
        case "xl":
          return 11;
      }
      return null;
    },
  },
};
</script>

<style>
</style>