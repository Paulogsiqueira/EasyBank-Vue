<template>
  <section :class="headerClass">
    <div class="header-half">
      <div class="header-text">
        <h1>Next generation digital banking</h1>
        <p>
          Take your financial life online. Your Easybank account will be a
          one-stop-shop for spending, saving, budgeting, investing, and much
          more.
        </p>
        <div class="header-button">
          <ButtonRequest text="Request Invite" />
        </div>
      </div>
    </div>
    <div class="header-img">
      <img
        class="header-blue"
        src="../../assets/img/Header/BackBlue.png"
        alt="Blue background image"
      />
      <img
        class="header-green"
        src="../../assets/img/Header/BackGreen.png"
        alt="Green background image"
      />
      <img
        class="header-phone"
        src="../../assets/img/Header/BackPhotos.png"
        alt="Phones background image"
      />
    </div>
  </section>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import ButtonRequest from "../Generics/ButtonRequest.vue";

export default defineComponent({
  components: { ButtonRequest },
  name: "HeaderBank",
  data() {
    return {
      headerClass: "header-container" as String,
    };
  },
  methods: {
    handleResize() {
      const screenWidth = window.innerWidth;
      if (screenWidth > 600) {
        this.headerClass = "header-container";
      }
    },
    changeBackground() {
      console.log(this.opacit)
      if (this.headerClass == "header-container") {
        this.headerClass = "header-container-opacity";
      } else {
        this.headerClass = "header-container";
      }
    },
  },
  watch: {
    // sempre que a propriedade opacity muda, esta função será chamada
    opacit() {
      this.changeBackground();
    }
  },
  props: {
    opacit: {
      type: Boolean,
    },
  },
  mounted() {
    window.addEventListener("resize", this.handleResize);
  },
});
</script>

<style scoped>
.header-container {
  min-height: 100%;
  display: flex;
  background: linear-gradient(rgba(45, 49, 77, 0), transparent);
}

.header-img {
  display: flex;
  justify-content: right;
  max-height: 700px;
  overflow: hidden;
  max-width: 100vw;
}
.header-blue {
  position: absolute;
  z-index: -2;
}
.header-green {
  position: absolute;
  z-index: -1;
  top: 0px;
}
.header-phone {
  position: absolute;
  z-index: 0;
  top: 0px;
}
.header-half {
  height: 700px;
  width: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.header-text {
  box-sizing: border-box;
  width: 60%;
}
.header-text h1 {
  font-size: 56px;
  font-family: "Public Sans", sans-serif;
  font-weight: 300;
  color: #2d314d;
}

.header-text p {
  font-size: 18px;
  font-family: "Public Sans", sans-serif;
  font-weight: 400;
  color: #9597a5;
  margin-bottom: 40px;
}
.header-button {
  width: 40%;
  min-width: 110px;
}

.header-img {
  min-width: 50%;
  display: flex;
  overflow: hidden;
}

@media (max-width: 1100px) {
  .header-blue {
    position: absolute;
    z-index: -2;
    scale: 0.8;
    right: -80px;
    top: 0px;
  }
  .header-green {
    position: absolute;
    z-index: -1;
    top: 0px;
    scale: 0.8;
    right: -60px;
  }
  .header-phone {
    position: absolute;
    z-index: 0;
    top: 0px;
    scale: 0.8;
    right: -60px;
  }
}
@media (max-width: 950px) {
  .header-blue {
    position: absolute;
    z-index: -2;
    scale: 0.7;
    right: -121px;
  }
  .header-green {
    position: absolute;
    z-index: -1;
    top: 0px;
    scale: 0.7;
    right: -90px;
  }
  .header-phone {
    position: absolute;
    z-index: 0;
    top: -100px;
    scale: 0.7;
    right: -97px;
  }
}

@media (max-width: 880px) {
  .header-blue {
    position: absolute;
    z-index: -2;
    scale: 0.9;
    right: -41px;
  }
  .header-green {
    position: absolute;
    z-index: -1;
    top: 0px;
    scale: 0.9;
    right: -30px;
  }
  .header-phone {
    position: absolute;
    z-index: 0;
    top: -100px;
    scale: 0.9;
    right: -32px;
  }
  .header-container {
    flex-direction: column-reverse;
  }
  .header-img {
    height: 500px;
  }
  .header-half {
    width: 100%;
  }

  .header-text {
    box-sizing: border-box;
    width: 88%;
    text-align: center;
  }

  .header-text h1 {
    font-size: 40px;
  }

  .header-text p {
    font-size: 15px;
    margin-bottom: 40px;
  }
  .header-button {
    margin: 0 auto;
  }
}

@media (max-width: 680px) {
  .header-blue {
    position: absolute;
    z-index: -2;
    scale: 0.7;
    right: -123px;
  }
  .header-green {
    position: absolute;
    z-index: -1;
    top: 0px;
    scale: 0.7;
    right: -90px;
  }
  .header-phone {
    position: absolute;
    z-index: 0;
    top: -100px;
    scale: 0.7;
    right: -97px;
  }
}

@media (max-width: 600px) {
  .header-container-opacity {
    min-height: 100%;
    display: flex;
    background: linear-gradient(rgba(45, 49, 77, 0.4), transparent);
    flex-direction: column-reverse;
  }
  .header-container {
    min-height: 100%;
    display: flex;
    background: linear-gradient(rgba(45, 49, 77, 0), transparent);
  }
  .header-blue {
    position: absolute;
    z-index: -2;
    scale: 0.7;
    right: -123px;
  }
  .header-green {
    position: absolute;
    z-index: -1;
    top: 0px;
    scale: 0.7;
    right: -90px;
  }
  .header-phone {
    position: absolute;
    z-index: 0;
    top: -100px;
    scale: 0.7;
    right: -97px;
  }

  .header-half {
    height: 400px;
  }
}

@media (max-width: 480px) {
  .header-blue {
    position: absolute;
    z-index: -2;
    scale: 0.6;
    right: -164px;
    top: -150px;
  }
  .header-green {
    position: absolute;
    z-index: -1;
    top: 0px;
    scale: 0.6;
    right: -121px;
    top: -80px;
  }
  .header-phone {
    position: absolute;
    z-index: 0;
    top: -250px;
    scale: 0.6;
    right: -129.5px;
  }
  .header-half {
    height: 300px;
  }

  .header-img {
    height: 350px;
  }
}
</style>
