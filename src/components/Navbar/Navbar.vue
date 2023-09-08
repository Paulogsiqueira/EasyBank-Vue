<template>
  <div class="navbar">
    <div class="navbar-logo">
      <img src="../../assets/img/logo.png" alt="EasyBank logo" />
    </div>
    <div class="navbar-links">
      <Button text="Home" buttonType="button-header" />
      <Button text="About" buttonType="button-header" />
      <Button text="Contact" buttonType="button-header" />
      <Button text="Blog" buttonType="button-header" />
      <Button text="Carrers" buttonType="button-header" />
    </div>
    <div class="navbar-button">
      <ButtonRequest text="Request Invite" />
    </div>
    <div class="navbar-list">
      <img :src="icon.toString()" @click="changeIcon" alt="Icon" />
    </div>
    <div v-if="hamb" class="show">
      <menu-hamburguer />
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import Button from "../Generics/Button.vue";
import ButtonRequest from "../Generics/ButtonRequest.vue";
import MenuHamburguer from "./MenuHamburguer.vue";

export default defineComponent({
  name: "Navbar",
  components: {
    Button,
    ButtonRequest,
    MenuHamburguer,
  },
  data() {
    return {
      icon: require("../../assets/icons/navbar/Hamb.png") as String,
      hamb: false as boolean,
    };
  },
  emits: ["menu"],
  mounted() {
    window.addEventListener("resize", this.handleResize);
  },
  methods: {
    changeIcon() {
      if (this.icon == require("../../assets/icons/navbar/Hamb.png")) {
        this.icon = require("../../assets/icons/navbar/Close.png");
        this.hamb = !this.hamb;
      } else {
        this.icon = require("../../assets/icons/navbar/Hamb.png");
        this.hamb = !this.hamb;
      }
      this.$emit("menu");
    },
    handleResize() {
      const screenWidth = window.innerWidth;
      if (screenWidth > 600) {
        this.hamb = false;
        this.icon = require("../../assets/icons/navbar/Hamb.png");
      }
    },
  },
});
</script>
<style scoped>
.navbar-list {
  display: none;
}
.navbar {
  width: 100%;
  background: white;
  margin-top: 0px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  height: 80px;
  z-index: 10;
  position: relative;
}

.navbar-links {
  display: flex;
  justify-content: space-between;
  height: 100%;
  align-items: center;
  width: 40%;
}
.navbar-button {
  min-width: 110px;
  width: 10%;
}

@media (max-width: 600px) {
  .navbar-links {
    display: none;
  }

  .navbar-button {
    display: none;
  }
  .navbar-list {
    display: inline-block;
    position: absolute;
    right: 50px;
  }

  .navbar-logo {
    position: absolute;
    left: 50px;
  }

  .hidden {
    display: none;
  }

  .show {
    display: inline;
  }
}
</style>

