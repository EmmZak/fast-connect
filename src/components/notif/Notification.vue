<template>
  <div class="" style="width: 100%">
    <!-- other screens -->
    <v-row
      class="rounded-sm white "
      justify="space-between"
      align="center"
      no-gutters
      style="opacity: 80%"
    >
      <v-col cols="2" class="text-centerr pa-0">
        <v-icon :color="iconColor" :size="iconFontSize"
          >mdi-account-box</v-icon
        >
      </v-col>
      <v-col cols="9" class="pa-0">
        <v-row class="pa-0" no-gutters>
          <v-col class="text-left" cols="12">
            <div
              class="black--text"
              :style="{ fontSize: titleFontSize + 'px' }"
            >
              Dispositif
            </div>
          </v-col>
          <v-col cols="12" class="text-left">
            <div
              class="black--text"
              :style="{ fontSize: messageFontSize + 'px' }"
            >
              {{ text }}
            </div>
          </v-col>
        </v-row>
      </v-col>
    </v-row>

    <!-- notif for mobile -->
    <v-row
      v-if="false"
      class="rounded-sm white hidden-sm-and-up"
      justify="space-between"
      align="center"
      no-gutters
      style="opacity: 80%"
    >
      <v-col cols="2" class="text-centerr pa-0">
        <v-icon class="green--text" :size="iconFontSize"
          >mdi-account-box</v-icon
        >
      </v-col>
      <v-col cols="7">
        <div class="black--text" :style="{ fontSize: titleFontSize + 'px' }">
          Dispositif
        </div>
      </v-col>
      <v-col cols="12">
        <div class="black--text text-center" :style="{ fontSize: messageFontSize + 'px' }">
          {{ text }}
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Notification",
  props: ["message"],
  computed: {
    iconColor(){
      return this.message.includes('souci') ? 'orange': 'green'
    },
    text() {
      let date = new Date();
      return `${date.getHours()}:${date.getMinutes()} - ${this.message}`;
    },
    iconFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 35;
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