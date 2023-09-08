<template>
  <section class="modal">
    <div class="modal-values">
      <div class="modal-values-title">
        <h3>{{ coinsValue }}K EasyBank Coins</h3>
      </div>
      <div class="modal-values-content">
        <p class="value-month">
          <span class="modal-input-value">${{ inputValue }}</span>
        </p>
        <p>
          <span>/ month</span>
        </p>
      </div>
    </div>

    <div class="modal-range-section">
      <input
        class="modal-range"
        type="range"
        min="10"
        max="40"
        v-model="inputValue"
        @input="updateRangeValue"
      />
      <p>Chose the quantity you can pay</p>
    </div>

    <div class="modal-options">
      <div class="modal-benefits">
        <div class="modal-benefit">
          <img src="../../assets/icons/club/check.png" alt="check" />
          <p class="benefits-item">EasyBank Coins every month</p>
        </div>
        <div class="modal-benefit">
          <img src="../../assets/icons/club/check.png" alt="check" />
          <p class="benefits-item">20% discount to buy new coins</p>
        </div>
        <div class="modal-benefit">
          <img src="../../assets/icons/club/check.png" alt="check" />
          <p class="benefits-item">Email reports</p>
        </div>
      </div>
      <div class="modal-button">
        <ButtonRequest text="Request Invite" />
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ButtonRequest from "../Generics/ButtonRequest.vue";

export default defineComponent({
  components: { ButtonRequest },
  name: "ClubModal",
  data() {
    return {
      inputValue: 25 as number,
      coinsValue: 2.5 as number,
    };
  },
  methods: {
    updateRangeValue(event: Event) {
      if (event.target) {
        this.inputValue = parseInt((event.target as HTMLInputElement).value);
        this.coinsValue = this.inputValue / 10;
      }
    },
  },
});
</script>

<style scoped>
.modal {
  width: 40%;
  max-width: 540px;
  display: flex;
  flex-direction: column;
  background-color: #dedcdc;
  margin: 0 auto;
  padding: 10px 30px;
  border-radius: 15px;
  margin-bottom: 8%;
  box-shadow: 10px 10px 10px rgba(0, 0, 0, 0.2);
  border: 1px solid #c4c4c4;
  height: 350px;
}

.modal-values-title {
  font-family: "Public Sans", sans-serif;
  color: #2d314d;
}

.modal-values-content {
  display: flex;
  align-items: center;
}
.modal-values {
  display: flex;
  justify-content: space-between;
  color: #2d314d;
}

.modal-input-value {
  font-size: 30px;
  font-weight: 900;
  color: #2d314d;
  text-align: center;
  align-content: center;
  align-items: center;
}
.modal-range {
  width: 70%;
  margin: 0 auto;
  appearance: none;
  border-radius: 10px;
  background: linear-gradient(to right, #33d35e 0%, #2ab6d9 100%);
  height: 8px;
}

.modal-range::-webkit-slider-thumb {
  appearance: none;
  background-color: #35cb5d;
  background-image: url("../../assets/icons/club/arrows.png");
  background-repeat: no-repeat;
  background-position: 7px 11px;
  border-radius: 30px;
  width: 35px;
  height: 35px;
  cursor: pointer;
  box-shadow: 3px 3px 5px rgba(53, 203, 93, 0.2);
}

.modal-range-section {
  margin: 0 auto;
  width: 100%;
  display: flex;
  justify-content: center;
  margin-top: 30px;
  display: flex;
  flex-direction: column;
}

.modal-range-section p {
  color: #848ead;
  margin: 25px auto;
  font-size: 16px;
  font-family: "Public Sans", sans-serif;
}

.modal-options {
  display: flex;
  justify-content: space-around;
  margin-top: 60px;
}

.modal-benefits {
  display: flex;
  flex-direction: column;
  font-size: 80%;
  color: #2d314d;
  justify-content: center;
  width: 50%;
  font-family: "Public Sans", sans-serif;
}

.modal-benefit {
  color: #2d314d;
  display: flex;
  align-items: center;
}

.modal-benefit p {
  color: #2d314d;
}
.modal-benefit img {
  height: 12px;
  margin-right: 5px;
}

.modal-button {
  width: 40%;
  min-width: 150px;
  height: 45px;
  margin: 25px auto 0px auto;
}

@media (max-width: 1100px) {
  .modal-benefits {
    font-size: 11px;
  }
}

@media (max-width: 930px) {
  .modal-benefits {
    font-size: 80%;
    margin: 0 auto;
    justify-content: center;
    align-items: center;
    width: 200px;
  }

  .modal-options {
    flex-direction: column;
    margin-top: 20px;
  }

  .modal {
    height: 450px;
  }
}

@media (max-width: 800px) {
  .modal-values {
    flex-direction: column;
    align-items: center;
  }
}

@media (max-width: 650px) {
  .modal-values {
    flex-direction: column;
    align-items: center;
  }
}

@media (max-width: 570px) {
  .modal {
    width: 60%;
  }
}

@media (max-width: 373px) {
  .modal-button {
    margin: 5px auto 0px auto;
  }
}
</style>