<template>
  <v-row
    class="rounded-sm grey"
    justify="space-between"
    align="center"
    no-gutters
  >
    <v-col cols="3" class="text-center pa-0">
      <v-icon class="red--text" :size="40">mdi-alert</v-icon>
    </v-col>
    <v-col cols="9" class="pa-0">
      <v-row class="pa-0" no-gutters>
        <v-col class="" cols="12">
          <div class="white--text">Dispositif</div>
        </v-col>
        <v-col cols="12">
          <div class="pa-0" :style="{ fontSize: '9.5px', color: 'white' }">
            Adresse - 12 rue de l'Yser
          </div>
          <div class="pa-0" :style="{ fontSize: '9.5px', color: 'white' }">
            Numéro sécu - 98765435678
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
      let str = `${new Date().toLocaleString().split(",")[1]} - ${
        this.message
      }`;
      return str;
    },
  },
};
</script>