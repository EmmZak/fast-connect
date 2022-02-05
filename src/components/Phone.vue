<template>
  <v-card
    width="90%"
    max-width="300px"
    min-height="300px"
    height="100%"
    style="
      border-radius: 15px;
      border: solid 7px black;
      background: linear-gradient(#e66465, #9198e5);
    "
  >
    <v-card-text class="darken-4 full-height pa-0">
      <v-row
        class="pa-1"
        style="height: 50"
        justify=""
        align=""
        no-gutters
        v-if="!this.call"
      >
        <v-col class="text-center" style="padding-top: 30%; padding-bottom: 15%">
          <div class="title-font white--text">
            <div class="title-font" :style="{ fontSize: timeFontSize + 'px' }">
              {{ time }}
            </div>
          </div>
          <div class="title-font white--text text-h5" style="padding-top: 5%">
            <div class="title-font" :style="{ fontSize: dateFontSize + 'px' }">
              {{ date }}
            </div>
          </div>
        </v-col>

        <SOSNotification v-if="this.sosNotif" />
        <Notification v-if="this.notif" :message="notifText" />
      </v-row>
      <v-row v-if="true" class="fill-height">
        <PhoneCall v-if="this.call" />
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script>
/* eslint-disable vue/no-unused-components */
import SOSNotification from "./SOSNotification.vue";
import Notification from "./Notification.vue";
import PhoneCall from "./PhoneCall.vue";

export default {
  name: "Phone",
  props: ["notif", "notifText", "sosNotif", "call"],
  components: {
    SOSNotification,
    Notification,
    PhoneCall,
  },
  data() {
    return {
      notification: {
        textOK: "Salut, j'ai un souci",
        textKO: "Salut, tout va bien",
        text: "Salut, j'ai un souci",
      },
    };
  },
  computed: {
    time() {
      let date = new Date();
      return date.getHours() + ":" + date.getMinutes();
    },
    date() {
      let date = new Date().toLocaleDateString("fr-FR", {
        weekday: "long",
        month: "long",
        day: "numeric",
      });
      return date;
    },
    timeFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 30;
        case "sm":
          return 32;
        case "md":
          return 32;
        case "lg":
          return 38;
        case "xl":
          return 42;
      }
      return null;
    },
    dateFontSize() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return 13;
        case "sm":
          return 16;
        case "md":
          return 14;
        case "lg":
          return 18;
        case "xl":
          return 22;
      }
      return null;
    },
  },
};
</script>

