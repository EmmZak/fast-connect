<template>
  <v-app>
    <Header />
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: { Header },
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