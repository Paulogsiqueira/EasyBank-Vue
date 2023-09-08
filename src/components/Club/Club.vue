<template>
  <section class="club">
    <h1>EasyBank Club</h1>
    <p>Sign-up for our 30-day trial. No credit card required.</p>
    <ClubModal />
  </section>
</template>

<script>
import { defineComponent } from "vue";
import ClubModal from "./ClubModal.vue";

export default defineComponent({
  components: { ClubModal },
  name: "Club",
});
</script>
<style scoped>
.club h1 {
  padding-left: 11%;
  font-size: 40px;
  font-family: "Public Sans", sans-serif;
  font-weight: 300;
  color: #2d314d;
  margin-top: 50px;
}

.club p {
  font-size: 18px;
  color: #9597a5;
  width: 50%;
  margin-left: 11%;
  margin-top: 50px;
  font-family: "Public Sans", sans-serif;
  margin-bottom: 100px;
}

@media (max-width: 700px) {
  .club h1 {
    text-align: center;
    padding-left: 0%;
  }

  .club p {
    text-align: center;
    width: 100%;
    margin:0px 0px 100px 0px;
  }
}
</style>