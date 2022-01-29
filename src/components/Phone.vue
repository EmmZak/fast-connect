<template>
  <div>
    <v-card width="250px" height="500px" class="black rounded-lg">
      <!-- screen -->
      <v-card-text class="black full-height  green">
        <div class="pa-2"><Notification /></div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
import Notification from "./Notification.vue";

export default {
  name: "Phone",
  components: {
    Notification,
  },
};
</script>

