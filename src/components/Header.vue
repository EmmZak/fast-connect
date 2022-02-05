<template>
  <v-app-bar
    
    app
    dark
    id="navbar"
  >
    <div v-if="false" class="text-h3">
      <div class="title-font">
        <span id="fast">FAST</span>
        <span id="contact">Contact</span>
      </div>
    </div>

    <div class="text-h3">
      <div class="title-fontt">
        <span id="fast">FAST</span>
        <span id="contact">Contact</span>
      </div>
    </div>

    <v-img
      v-if="false"
      class="mx-2"
      :src="require('./../assets/logo.svg')"
      max-height="70"
      max-width="70"
      contain
    ></v-img>

    <v-btn
      v-if="false"
      href="https://github.com/vuetifyjs/vuetify/releases/latest"
      target="_blank"
      text
    >
      <v-icon>mdi-open-in-new</v-icon>
    </v-btn>
  </v-app-bar>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style>
#navbar {
  background-color: rgb(255, 255, 255);
}

#fast {
  color: #00b8ac;
  font-weight: bold;
}

#contact {
  color: #3c3c3c;
}
</style>