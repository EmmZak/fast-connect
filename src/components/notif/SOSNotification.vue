<template>
  <v-row
    class="rounded-sm white"
    justify="space-between"
    align="center"
    no-gutters
    style="opacity: 80%"
  >
    <v-col cols="2" class="text-center pa-0">
      <v-icon class="red--text" :size="iconFontSize">mdi-alert-circle</v-icon>
    </v-col>
    <v-col cols="9" class="pa-0">
      <v-row class="pa-0" no-gutters>
        <v-col class="text-left" cols="12">
          <div class="black--text" :style="{ fontSize: titleFontSize + 'px' }">
            Dispositif
          </div>
        </v-col>
        <v-col class="text-left" cols="12" style="padding-top: 2%">
          <div
            class="pa-0 black--text"
            style="line-height: 1.3; letter-spacing: 0"
            :style="{ fontSize: messageFontSize + 'px' }"
          >
            Adresse - 12 rue de l'Yser, Numéro sécu - 98765435678
          </div>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "SOSNotification",
  computed: {
    text() {
      let date = new Date()
      return `${date.getHours()}:${date.getMinutes()} - ${this.message}`
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