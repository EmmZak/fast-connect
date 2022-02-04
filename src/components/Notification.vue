<template>
  <v-row class="rounded-sm grey" justify="space-between" align="center" no-gutters>
    <v-col cols="2" class="text-center pa-0">
      <v-icon class="yellow--text" :size="40">mdi-account-box</v-icon>
    </v-col>
    <v-col cols="9" class="pa-0">
      <v-row class="pa-0" no-gutters>
        <v-col class="" cols="12">
          <div class="white--text">Dispositif</div>
        </v-col>
        <v-col cols="12">
          <div :style="{ fontSize: '9.5px', color: 'white' }">
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
  },
};
</script>

<style>
</style>