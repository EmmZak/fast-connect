<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="text-h5"><span class="title-font">FASTContact</span></div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>

<style>
.full-height {
  height: 100%;
}

.full-width {
  width: 100%;
}

.title-font {
  font-family: "Open Sans", sans-serif;
}
</style>