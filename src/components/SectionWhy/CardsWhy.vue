<template>
  <div class="cards">
    <div class="cards-container">
      <Card v-for="imagem in imagens" :key="imagem.address" :imagem="imagem" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Card from "../Generics/Card.vue";
import ICard from "../../Interface/ICard";

export default defineComponent({
  name: "CardsWhy",
  components: { Card },
  data() {
    return {
      imagens: [
        {
          address: require("../../assets/img/Why/online.png"),
          alt: "Online Icon",
          title: "Online Banking",
          description:
            "Our modern web and mobile applications allow you to keep track of your finances wherever you are in the world.",
        },
        {
          address: require("../../assets/img/Why/simple.png"),
          alt: "Simple Budgeting Icon",
          title: "Simple Budgeting",
          description:
            "See exactly where your money goes each month. Receive notifications when you’re close to hitting your limits.",
        },
        {
          address: require("../../assets/img/Why/fast.png"),
          alt: "Fast Icon",
          title: "Fast Onboarding",
          description:
            "We don’t do branches. Open your account in minutes online and start taking control of your finances right away.",
        },
        {
          address: require("../../assets/img/Why/api.png"),
          alt: "API Icon",
          title: "Open API",
          description:
            "Manage your savings, investments, pension, and much more from one account. Tracking your money has never been easier.",
        },
      ] as ICard[],
    };
  },
});
</script>

<style scoped>
.cards {
  margin-top: 70px;
}

.cards-container {
  display: flex;
  justify-content: space-between;
  width: 80%;
  margin: 0 auto;
}

@media (max-width: 600px) {
  .cards-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 80%;
    margin: 0 auto;
  }
}
</style>