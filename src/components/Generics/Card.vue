<template>
  <div class="card">
    <div class="card-img">
      <img :src="imagem.address" :alt="imagem.alt" />
    </div>
    <h3>{{ imagem.title }}</h3>
    <p>{{ imagem.description }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "WhyBank",
  props: {
    imagem: {
      type: Object,
      required: true,
    },
  },
});
</script>

<style scoped>
.card-img {
  background: linear-gradient(to right, #33d35e 0%, #2ab6d9 100%);
  width: 72px;
  height: 72px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
}

.card h3 {
  font-size: 24px;
  font-weight: 300;
  font-family: "Public Sans", sans-serif;
  color: #2d314d;
}

.card p {
  font-weight: 300;
  font-family: "Public Sans", sans-serif;
  color: #9597a5;
  font-size: 16px;
}
.card {
  width: 18%;
}

@media (max-width: 600px) {
  .card {
    width: 100%;
  }
  .card-img {
    display: flex;
    margin: 0 auto;
    border-radius: 50%;
  }

  .card h3 {
    font-size: 20px;
    font-weight: 300;
    font-family: "Public Sans", sans-serif;
    color: #2d314d;
    text-align: center;
  }

  .card p {
  font-weight: 300;
  font-family: "Public Sans", sans-serif;
  color: #9597a5;
  font-size: 15px;
  text-align: center;
}
}
</style>