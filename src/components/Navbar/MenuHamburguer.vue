<template>
  <div class="menu">
    <p class="menu-options">Home</p>
    <p class="menu-options">About</p>
    <p class="menu-options">Contact</p>
    <p class="menu-options">Blog</p>
    <p class="menu-options">Careers</p>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "MenuHamburguer",
});
</script>
<style scoped>
.menu {
  width: 87%;
  background-color: rgb(252, 252, 252);
  position: absolute;
  top: 100px;
  height: 300px;
  text-align: center;
  border-radius: 10px;
  left:6.5%;
}

.menu-options {
  margin: 30px auto;
  font-size: 18px;
  font-family: "Public Sans", sans-serif;
  font-weight: 400;
  color: #2D314D;
}

.menu-options:hover{
    scale:1.2;
    font-weight: 600;
}
</style>
