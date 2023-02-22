<script setup>
import article_component from "./components/article_component.vue";
import header_component from "./components/header_component.vue";
import article_modal_component from "./components/article_modal_component.vue";
</script>

<template>
  <header>
    <header_component />
  </header>
  <section class="article_display">
    <h3 class="heading">News Articles</h3>
    <article_modal_component v-if="modal_bool"  :modal_obj="modal_prop"/>
    <article_component
      v-for="article in article_array"
      @click="modal_bool = true; modal_prop=article"
      :article_obj="article"
    />
  </section>
</template>

<script>
export default {
  data() {
    return {
      article_array: [],
      modal_bool: false,
      modal_prop:{
        source:{name:'',id:''},
        author:'',
        title:'',
        description:'',
        url:'',
        urlToImage:'',
        publishedAt:'',
        content:''
      }
    };
  },

  methods: {
    async data_fetch() {
      const response = await fetch(
        "https://newsapi.org/v2/everything?q=dogs&apiKey=a538540a4b4c4ea48ff8f0b4afb141ec"
      );
      const received_data = await response.json();
      this.article_array = received_data.articles;
    },
  },
  created() {
    this.data_fetch();
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700&display=swap");

* {
  font-family: "Poppins", sans-serif;
}
.article_display {
  margin: 10px;
  display: flex;
  flex-direction: column;
  position: relative;
}

.heading {
  text-align: center;
  font-weight: 400;
}
</style>
