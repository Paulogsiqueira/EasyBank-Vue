<template>
  <div class="menu">
    <option class="menu-options">Home</option>
    <option class="menu-options">About</option>
    <option class="menu-options">Contact</option>
    <option class="menu-options">Blog</option>
    <option class="menu-options">Careers</option>
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
