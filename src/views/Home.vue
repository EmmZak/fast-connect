<template>
  <v-container class="" fluid>
    <v-row justify="center">
      <div class="">
        <Phone
          :notif="phone1.notif"
          :notifText="notifText"
          :sosNotif="sosNotif"
          :call="phone1.call"
        />
      </div>
      <div class="pa-2"></div>
      <div>
        <Kiosk @call="call" @sos="sos" @notif="notif" />
      </div>
      <div class="pa-2"></div>
      <div class="">
        <Phone
          :notif="phone2.notif"
          :notifText="notifText"
          :sosNotif="sosNotif"
          :call="phone2.call"
        />
      </div>
      <!-- <v-col class="red" cols="3">
        <Phone />
      </v-col>
      <v-col class="green" cols="6"></v-col>
      <v-col class="red" cols="3">
        <Phone />
      </v-col> -->
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
      sosNotif: false,
      notifText: "default",
      phone1: {
        notif: false,
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
      console.log("call fired", event);
      if (event == "Emmanuel") {
        this.phone1.call = true;
      } else {
        this.phone2.call = true;
      }
      setTimeout(() => {
        if (event == "Emmanuel") {
          this.phone1.call = false;
        } else {
          this.phone2.call = false;
        }
      }, 5000);
    },
    sos() {
      this.sosNotif = true
    },
    notif(event) {
      console.log("event", event)
      if (event == "ok") {
        this.notifText = "Salut, tout va bien";
      } else {
        this.notifText = "Salut, j'ai un souci";
      }
      this.phone1.notif = true;
      this.phone2.notif = true;
    },
  },
};
</script>
