<template>
  <div class="container">
    <Navbar @menu="changeBack" />
    <HeaderBank :opacit="opacity"/>
    <WhyBank />
    <ArticlesGallery />
    <Club/>
    <FooterBank />
  </div>
</template>


<script lang="ts">
import { defineComponent } from "vue";
import Navbar from "./components/Navbar/Navbar.vue";
import FooterBank from "./components/Footer/FooterBank.vue";
import HeaderBank from "./components/Header/HeaderBank.vue";
import WhyBank from "./components/SectionWhy/WhyBank.vue";
import ArticlesGallery from "./components/SectionArticle/ArticlesGallery.vue";
import "normalize.css";
import Club from "./components/Club/Club.vue";

export default defineComponent({
  name: "App",
  components: { Navbar, WhyBank, HeaderBank, ArticlesGallery, FooterBank, Club },
  methods: {
    changeBack: function () {
      this.opacity = !this.opacity;

    },
  },
  props: {
    opacity: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      opacity: this.$props.opacity,
    };
  },
});
</script>
