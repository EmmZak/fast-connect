<template>
  <v-row class="full-height grey"  no-gutters align="center">
    <v-col cols="12" class="text-center">
      <div class="text-h4 white--text">
        <span class="title-font"> Dispositif </span>
      </div>
    </v-col>
    <v-col cols="12" class="">
      <v-row justify="space-around" no-gutters>
        <v-col cols="6" class="">
          <CallAction type="accept" />
        </v-col>
         <v-col cols="6" class="">
          <CallAction type="deny" />
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<script>
import CallAction from "./CallAction.vue"

export default {
  name: "Call",
  components: {CallAction}
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