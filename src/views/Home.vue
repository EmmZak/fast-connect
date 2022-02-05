<template>
  <v-container class="" fluid>
    <v-row v-if="true" justify="space-around" class="hidden-md-and-up">
      <v-col md="12" sm="12" cols="12" class="purple">
        <Kiosk @call="call" @sos="sos" @notif="notif" />
      </v-col>
      <v-col md="6" sm="4" cols="6" class="red">
        <Phone
          :notif="phone1.notif"
          :notifText="notifText"
          :sosNotif="sosNotif"
          :call="phone1.call"
        />
      </v-col>
      <v-col md="6" sm="4" cols="6" class="">
        <Phone
          :notif="phone2.notif"
          :notifText="notifText"
          :sosNotif="sosNotif"
          :call="phone2.call"
        />
      </v-col>
    </v-row>

    <v-row justify="center" class="hidden-sm-and-down text-center">
      <v-col  class="red">
        <Phone
          v-if="true"
          :notif="phone1.notif"
          :notifText="notifText"
          :sosNotif="sosNotif"
          :call="phone1.call"
        />
      </v-col>
      <v-col xl="7" lg="7" md="7" class="green">
        <Kiosk @call="call" @sos="sos" @notif="notif" />
      </v-col>
      <v-col  class="yellow">
        <Phone
          v-if="true"
          :notif="phone2.notif"
          :notifText="notifText"
          :sosNotif="sosNotif"
          :call="phone2.call"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
/* eslint-disable vue/no-unused-components */
import Phone from "../components/Phone";
import Kiosk from "../components/Kiosk";

export default {
  name: "Home",
  components: {
    Kiosk,
    Phone,
  },
  data() {
    return {
      block: false,
      sosNotif: false,
      notifText: "Salut, j'ai un souci",
      phone1: {
        notif: true,
        call: false,
      },
      phone2: {
        notif: false,
        call: false,
      },
    };
  },
  methods: {
    call(event) {
      if (this.block) {
        return;
      }
      this.block = true;
      console.log("call fired", event);
      if (event == "Emmanuel") {
        this.phone1.call = true;
      } else {
        this.phone2.call = true;
      }

      let audio = new Audio(require("./../../public/call-12.mp3"));
      audio.play();

      setTimeout(() => {
        if (event == "Emmanuel") {
          this.phone1.call = false;
        } else {
          this.phone2.call = false;
        }
        this.block = false;
        audio.stop();
      }, 12000);
    },
    sos() {
      if (this.block) {
        return;
      }
      this.block = true;

      this.sosNotif = true;

      let audio = new Audio(require("./../../public/notif.mp3"));
      audio.play();

      setTimeout(() => {
        this.sosNotif = false;
        this.block = false;
        audio.stop();
      }, 5000);
    },
    notif(event) {
      if (this.block) {
        return;
      }
      this.block = true;

      console.log("event", event);
      if (event == "ok") {
        this.notifText = "Salut, tout va bien";
      } else {
        this.notifText = "Salut, j'ai un souci";
      }

      let audio = new Audio(require("./../../public/notif.mp3"));
      audio.play();

      this.phone1.notif = true;
      this.phone2.notif = true;
      setTimeout(() => {
        this.phone1.notif = false;
        this.phone2.notif = false;
        this.block = false;
        //audio.stop();
      }, 5000);
    },
  },
};
</script>
