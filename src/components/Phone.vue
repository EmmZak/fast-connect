<template>
  <div>
    <v-card width="250px" height="500px" class=" rounded-lg">
      <!-- screen -->
      <!-- <div class="pa-2 green">
        <div class="pa-1 yellow">ok</div>
      </div> -->

      <v-card-text class="blue full-height">
        <v-row
          class="purple fill-height pa-0"
          justify="center"
          align="center"
          no-gutters
          v-if="true"
        >
          <div class="fill-height">
            <div class="title-font white--text text-h4">
              <div class="title-font">{{ time }}</div>
            </div>
            <div class="title-font white--text text-h5">
              <div class="title-font">{{ date }}</div>
            </div>
          </div>

          <Notification :message="notification.text" />
        </v-row>
        <v-row v-if="false" class="fill-height">
          <Call v-if="true" />
        </v-row>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
/* eslint-disable vue/no-unused-components */
import Notification from "./Notification.vue";
import Call from "./Call.vue";

export default {
  name: "Phone",
  components: {
    Notification,
    Call,
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

