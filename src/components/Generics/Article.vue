<template>
  <div class="article">
    <div class="article-img">
      <img
        class="article-img-photo"
        :src="article.address"
        :alt="article.alt"
      />
    </div>
    <div class="article-text">
      <p class="article-author">By {{ article.author }}</p>
      <h3>{{ article.title }}</h3>
      <p class="article-description">{{ article.description }}</p>
    </div>
  </div>
</template>
  
  <script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Article",
  props: {
    article: {
      type: Object,
      required: true,
    },
  },
});
</script>
  <style scoped>
.article {
  width: 23%;
  background-color: #ffffff;
  border-radius: 10px;
}

.article-img-photo {
  width: 100%;
}
.article-author {
  font-weight: 400;
  font-family: "Public Sans", sans-serif;
  color: #9597A5;
  font-size: 10px;
  margin-top: 15%;
}

.article h3 {
  font-weight: 300;
  font-family: "Public Sans", sans-serif;
  color: #2d314d;
  font-size: 16px;
  margin-bottom: 0px;
  margin-top: 0px;
}

.article h3:hover {
  color: #30c88f;
  cursor: pointer;
}

.article-text {
  width: 82%;
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  justify-content: flex-start;
  padding-right: 30px;
  box-sizing: border-box;
}
.article-description {
  font-weight: 400;
  font-family: "Public Sans", sans-serif;
  color: #9597a5;
  font-size: 13px;
}

@media (max-width: 700px) {
  .article {
    width: 45%;
    margin-bottom: 30px;
  }
}

@media (max-width: 400px) {
  .article {
    width: 100%;
    margin-bottom: 30px;
  }
}
</style>