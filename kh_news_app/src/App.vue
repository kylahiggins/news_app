<script setup>
import article_component from './components/article_component.vue'
import header_component from './components/header_component.vue'
</script>

<template>
  <header>
  <header_component/>

  </header>

  <section class="article_display">
    <h3 class="heading">News Articles</h3>
    <article_component/>
  </section>

  


</template>

<style scoped>

*{
  font-family:-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.article_display{
  margin: 10px;
  display: flex;
  /* align-items: center; */
  flex-direction: column;
}

.heading{
  text-align: center;
}

</style>