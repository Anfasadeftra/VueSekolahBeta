<template>
  <div>
    <div v-for="(article, index) in articles" :key="index">
      <h2>{{ article.title }}</h2>
      <img :src="article.img" :alt="article.title" width="500px"/>
      <p>{{ article.content }}</p>
      <router-link :to="'/article/' + index">Baca Selengkapnya</router-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    articles: Array,
  },
};
</script>