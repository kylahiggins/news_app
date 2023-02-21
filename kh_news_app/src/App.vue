<script setup>
// import article_component from './components/article_component.vue'
import header_component from './components/header_component.vue'
</script>

<template>
  <header>
  <header_component/>

  </header>

  <section class="article_display">
    <h3>News Articles</h3>
  </section>


</template>

<style scoped>

*{
  font-family:-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  margin: 5px;
}

.article_display{
  margin-top: 20px;
  text-align: center;
  display: flex;
}

</style>