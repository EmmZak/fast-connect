<template>
  <div>
    <v-card width="800px" height="500px" class="rounded-lg">
      <v-card-text>
        <v-row justify="space-around" no-gutters>
          <v-col cols="4" class="text-center" @click='$emit("notif", "ok")'>
            <v-icon style="font-size: 15vw" color="green"
              >mdi-emoticon-happy</v-icon
            >
          </v-col>
          <v-col cols="4" class="text-center" @click='$emit("notif", "ko")'>
            <v-icon style="font-size: 15vw" color="red"
              >mdi-emoticon-sad</v-icon
            >
          </v-col>
        </v-row>
      </v-card-text>
      <v-card-actions>
        <v-row justify="center" align="center" no-gutters>
          <v-col class="text-center" @click='$emit("call", "Emmanuel")'>
            <v-icon style="font-size: 8vw">mdi-phone</v-icon>
            <div class="text-h6">
              <div class="title-font">Emmanuel</div>
            </div>
          </v-col>
          <v-col class="text-center" @click='$emit("sos")'>
            <div class="text-h1">
              <div class="red white--text" style="border-radius: 30px">
                <div class="title-font">SOS</div>
              </div>
            </div>
          </v-col>
          <v-col class="text-center" @click='$emit("call", "Alexandre")' >
            <v-icon style="font-size: 8vw">mdi-phone</v-icon>
            <div class="text-h6">
              <div class="title-font">Alexandre</div>
            </div>
          </v-col>
        </v-row>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "Kiosk",
};
</script>

<style>
</style>