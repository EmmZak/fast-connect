<template>
  <v-card
    style="height: 100%; width: 100%; border: solid 7px grey; z-index: 1"
    class="rounded-lg kiosk"
  >
    <v-card-text class="">
      <v-row style="" justify="space-around" no-gutters>
        <v-col cols="4" class="text-center" @click="$emit('notif', 'ok')">
          <v-icon :size="emojiFontSize" color="green"
            >mdi-emoticon-happy</v-icon
          >
        </v-col>
        <v-col cols="4" class="text-center" @click="$emit('notif', 'ko')">
          <v-icon :size="emojiFontSize" color="red">mdi-emoticon-sad</v-icon>
        </v-col>
      </v-row>
    </v-card-text>
    <v-card-actions class="">
      <v-row justify="space-around" align="center" no-gutters>
        <v-col cols="3" class="text-center" @click="$emit('call', 'Emmanuel')">
          <v-icon style="font-size: 8vw">mdi-phone</v-icon>
          <div class="text-body-1">
            <div class="title-font">Emmanuel</div>
          </div>
        </v-col>
        <v-col cols="3" class="text-center" @click="$emit('sos')">
          <div class="">
            <div class="red white--text" style="border-radius: 30px">
              <div
                class="title-font"
                style="font-sizee: 40px"
                :style="{ fontSize: sosFontSize + 'px' }"
              >
                SOS
              </div>
            </div>
          </div>
        </v-col>
        <v-col cols="3" class="text-center" @click="$emit('call', 'Alexandre')">
          <v-icon style="font-size: 8vw">mdi-phone</v-icon>
          <div class="text-body-1">
            <div class="title-font">Alexandre</div>
          </div>
        </v-col>
      </v-row>
    </v-card-actions>
  </v-card>
</template>

<script>
/* eslint-disable vue/no-unused-components */
import KioskCall from "./call/KioskCall.vue";

export default {
  name: "Kiosk",
  props: ["isCalling"],
  components: { KioskCall },
  computed: {
    emojiFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 100;
        case "sm":
          return 175;
        case "md":
          return 175;
        case "lg":
          return 235;
        case "xl":
          return 300;
      }
      return null;
    },
    sosFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 22;
        case "sm":
          return 32;
        case "md":
          return 32;
        case "lg":
          return 50;
        case "xl":
          return 40;
      }
      return null;
    },
  },
};
</script>

<style>
.kiosk {
  border: solid 10px blue;
  background-color: rgb(211, 210, 210);
}
</style>