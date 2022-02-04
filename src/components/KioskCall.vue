<template>
  <v-card elevation="5" width="75%" height="50%">
    <v-card-text> Appel en cours ... </v-card-text>
    <v-card-actions class="justify-center">
      <div class="text-center blue" style="width: 75%">
        <v-btn color="red" width="100%">
          <div class="text-h6 white--text">
            <div class="title-font">Annuler</div>
          </div>
        </v-btn>
      </div>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  name: "KioskCall",
};
</script>