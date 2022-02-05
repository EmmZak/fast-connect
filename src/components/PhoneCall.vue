<template>
  <v-row class="full-height" no-gutters align="center">
    <v-col cols="12" class="text-center">
      <div class="text-h4 white--text">
        <div class="title-font" :style="{ fontSize: titleFontSize + 'px' }">
          Dispositif
        </div>
      </div>
    </v-col>
    <v-col cols="12" class="">
      <v-row justify="space-around" no-gutters>
        <v-col cols="6" class="">
          <CallAction
            :textFontSize="textFontSize"
            :iconFontSize="iconFontSize"
            type="accept"
          />
        </v-col>
        <v-col cols="6" class="">
          <CallAction
            :textFontSize="textFontSize"
            :iconFontSize="iconFontSize"
            type="deny"
          />
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
import CallAction from "./CallAction.vue";

export default {
  name: "Call",
  components: { CallAction },
  computed: {
    iconFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 30;
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
    textFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 10;
        case "sm":
          return 11;
        case "md":
          return 12;
        case "lg":
          return 15;
        case "xl":
          return 16;
      }
      return null;
    },
    titleFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 20;
        case "sm":
          return 24;
        case "md":
          return 22;
        case "lg":
          return 28;
        case "xl":
          return 32;
      }
      return null;
    },
  },
};
</script>

<style>
.square {
  color: green;
  position: relative;
  width: 50%;
}

.square:after {
  content: "";
  display: block;
  padding-bottom: 100%;
}
</style>