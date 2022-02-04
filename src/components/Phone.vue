<template>
  <div>
    <v-card width="250px" height="500px" class="rounded-lg">
      <!-- screen -->
      <!-- <div class="pa-2 green">
        <div class="pa-1 yellow">ok</div>
      </div> -->

      <v-card-text class="grey darken-4 full-height">
        <v-row
          class="pa-0"
          style="height: 50%"
          justify="center"
          align="center"
          no-gutters
          v-if="!this.call"
        >
          <v-col class="text-center">
            <div class="title-font white--text text-h3">
              <div class="title-font">{{ time }}</div>
            </div>
            <div class="title-font white--text text-h5">
              <div class="title-font">{{ date }}</div>
            </div>
          </v-col>

          <SOSNotification v-if="this.sosNotif" />
          <Notification v-if="this.notif" :message="notifText" />
        </v-row>
        <v-row class="fill-height">
          <PhoneCall v-if="this.call" />
        </v-row>
      </v-card-text>
    </v-card>
  </div>
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
      return new Date().toLocaleString().split(", ")[1];
    },
    date() {
      return new Date().toLocaleString().split(", ")[0];
    },
  },
};
</script>

