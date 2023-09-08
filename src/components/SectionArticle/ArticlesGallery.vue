<template>
  <div class="articles">
    <h3>Latest Articles</h3>
    <div class="articles-container">
      <Article
        v-for="article in articles"
        :key="article.address"
        :article="article"
      />
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import IArticle from "../../Interface/IArticle";
import Article from "../Generics/Article.vue";

export default defineComponent({
  name: "ArticlesGallery",
  components: { Article },
  data() {
    return {
      articles: [
        {
          address: require("../../assets/img/Articles/money.png"),
          alt: "Money image",
          title: "Receive money in any currency with no fees",
          author: "Claire Robinson",
          description:
            "The world is getting smaller and we’re becoming more mobile. So why should you be forced to only receive money in a single …",
        },
        {
          address: require("../../assets/img/Articles/dinner.png"),
          alt: "Dinner image",
          title: "Treat yourself without worrying about money",
          author: "Wilson Hutton",
          description:
            "Our simple budgeting feature allows you to separate out your spending and set realistic limits each month. That means you …",
        },
        {
          address: require("../../assets/img/Articles/plane.png"),
          alt: "Plane image",
          title: "Take your Easybank card wherever you go",
          author: "Wilson Hutton",
          description:
            "We want you to enjoy your travels. This is why we don’t charge any fees on purchases while you’re abroad. We’ll even show you …",
        },
        {
          address: require("../../assets/img/Articles/live.png"),
          alt: "Live image",
          title: "Our invite-only Beta accounts are now live!",
          author: "Claire Robinson",
          description:
            "After a lot of hard work by the whole team, we’re excited to launch our closed beta. It’s easy to request an invite through the site ...",
        },
      ] as IArticle[],
    };
  },
});
</script>
<style scoped>
.articles {
  padding-top: 5%;
  padding-bottom: 5%;
  background-color: #fafafa;
}

.articles h3 {
  font-size: 40px;
  font-family: "Public Sans", sans-serif;
  font-weight: 300;
  color: #2d314d;
  padding-left: 11%;
}

.articles-container {
  display: flex;
  width: 78%;
  justify-content: space-between;
  margin: 0 auto;
}

@media (max-width: 700px) {
  .articles-container {
    flex-direction: row;
    flex-wrap: wrap;
  }

  .articles h3 {
    font-size: 40px;
    font-family: "Public Sans", sans-serif;
    font-weight: 300;
    color: #2d314d;
    text-align: center;
    padding-left: 0%;
  }
}

@media (max-width: 400px) {
  .articles-container {
    flex-direction: column;
  }

  .articles h3 {
    font-size: 40px;
    font-family: "Public Sans", sans-serif;
    font-weight: 300;
    color: #2d314d;
    text-align: center;
    padding-left: 0%;
  }
}
</style>
