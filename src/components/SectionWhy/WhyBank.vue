<template>
  <div class="why-bank">
    <div class="why-bank-question">
      <h1>Why choose Easybank?</h1>
      <p>
        We leverage Open Banking to turn your bank account into your financial
        hub. Control your finances like never before.
      </p>
    </div>
    <CardsWhy />
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import CardsWhy from "./CardsWhy.vue";

export default defineComponent({
  name: "WhyBank",
  components: { CardsWhy },
});
</script>

<style scoped>
.why-bank {
  background-color: #f4f5f7;
  border: 1px solid #f4f5f7;
  font-size: 40px;
  padding-bottom: 5%;
}

.why-bank-question h1 {
  padding-left: 10%;
  font-size: 40px;
  font-family: "Public Sans", sans-serif;
  font-weight: 300;
  color: #2d314d;
  margin-top: 110px;
}

.why-bank-question p {
  font-size: 18px;
  color: #9597a5;
  width: 38%;
  margin-left: 10%;
  margin-top: 50px;
  font-family: "Public Sans", sans-serif;
}

@media (max-width: 600px) {
  .why-bank-question h1 {
    text-align: center;
    font-size: 32px;
    margin-top: 110px;
    padding-left:0%;
    margin-left: 6.5%;
    width: 87%;
  }

  .why-bank-question p {
    font-size: 15px;
    text-align: center;
    width: 87%;
    margin-left: 6.5%;
    
    
  }
}
</style>
