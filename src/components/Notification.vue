<template>
  <v-row class="rounded-sm grey" align="center" >
    <div class="">
      <v-icon class="yellow--text" :size="50">mdi-account-box</v-icon>
    </div>
    <div class="">
      <div class="white--text font-weight-bold" :style="{ fontSize: '14px' }">
        <div class="title-font">Mme Dupont</div>
      </div>
      <div class="white--text title-font" :style="{ fontSize: '14px' }">
        {{ text }}
      </div>
    </div>

    <!-- <v-col cols="2" class="text-center pa-0 ">
      <v-icon class="green--text" :size="50">mdi-account-box</v-icon>
    </v-col>
    <v-col cols="9" class="pa-0 ">
      <v-row class="pa-0" no-gutters>
        <v-col class="" cols="12">
          <div class="white--text">Mme Dupont</div>
        </v-col>
        <v-col cols="12">
          <div :style="{ fontSize: '9.5px', color: 'white' }">
            {{ text }}
          </div>
        </v-col>
      </v-row>
    </v-col> -->
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