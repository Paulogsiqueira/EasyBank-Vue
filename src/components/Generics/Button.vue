<template>
  <div :class=buttonType>
    <p>{{ text }}</p>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Button",
  props: {
    text: {
      type: String,
    },
    buttonType:{
      type:String
    }
  }
});
</script>

<style scoped>
.button-header {
  color: #9597a5;
  height: 100%;
  display: flex;
  align-items: center;
  font-size: 14px;
  font-family: "Public Sans", sans-serif;
  font-weight: 400;
  margin:0 5px;
}

.button-header:hover {
  border-bottom: 4px solid;
  border-image: linear-gradient(to right, #33d35e 0%, #2ab6d9 100%) 1;
  cursor: pointer;
}

.button-footer{
  font-size: 15px;
  font-family: "Public Sans", sans-serif;
  font-weight: 400;
  color:#FFFFFF;
  height: 32%;
  display: flex;
  align-items: center;
  width: 160px;
  justify-content: center;
}

.button-footer:hover{
  color:#30C88F;
  cursor: pointer;
}

@media (max-width: 600px) {
  .button-footer{
  font-size: 15px;
  font-family: "Public Sans", sans-serif;
  font-weight: 400;
  color:#FFFFFF;
  height: 30px;
  display: flex;
  align-items: center;
  width: 100px;
  justify-content: center;
}
}
</style>