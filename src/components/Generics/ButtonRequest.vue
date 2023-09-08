<template>
  <div class="button">
    <p>{{ text }}</p>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ButtonRequest",
  props: {
    text: {
      type: String,
    },
  },
});
</script>
<style scoped>

.button {
  min-width: 100%;
  background: linear-gradient(to right, #33d35e 0%, #2ab6d9 100%);
  height: 100%;
  border-radius: 30px;
  display: flex;
  justify-content: center;
  color: white;
  font-size: 14px;
  font-family:"Public Sans", sans-serif;
  font-weight: 700;
}

.button:hover{
    opacity: 40%;
    cursor:pointer;
}
</style>
