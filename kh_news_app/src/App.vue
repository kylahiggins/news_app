<script setup>
import article_component from "./components/article_component.vue";
import header_component from "./components/header_component.vue";
import article_modal_component from "./components/article_modal_component.vue";
</script>

<template>

  <!-- header -->

  <header>
    <link
      rel="stylesheet"
      href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200"
    />

    <div class="header_container">
      <div class="nav_item">
        <span class="material-symbols-outlined">menu</span>
      </div>

      <div class="nav_item">
        <div class="logo_img">
          <img src="./assets/images/Asset 1.png" alt="news icon" />
        </div>
      </div>

      <div class="nav_item" @click="search_click = !search_click">
        <span class="material-symbols-outlined">search</span>
      </div>
    </div>
    <div v-if="search_click" class="search_container">
      <div class="search_input">
        <input type="text" placeholder="Search" v-model="search_query" />
        <div class="search_btn" @click="data_fetch"><span class="material-symbols-outlined arrow">
    arrow_forward
    </span>
    </div>
      </div>
    </div>
  </header>

<!-- article section -->

  <section class="article_display">
    <h3 class="heading">News Articles</h3>
    <article_modal_component v-if="modal_bool" :modal_obj="modal_prop" />
    <article_component
      v-for="article in article_array" @click="modal_bool = true; modal_prop = article;" :article_obj="article"
    />
  </section>
</template>


// script section  ----------------------------------------------------

<script>
export default {
  data() {
    return {
      search_click: true,
      search_query: "apple",
      article_array: [],
      modal_bool: false,
      modal_prop: {
        source: { name: "", id: "" },
        author: "",
        title: "",
        description: "",
        url: "",
        urlToImage: "",
        publishedAt: "",
        content: "",
      },
    };
  },

  methods: {
    async data_fetch() {
      const response = await fetch(
        'https://newsapi.org/v2/everything?q= '+ this.search_query +'&apiKey=a538540a4b4c4ea48ff8f0b4afb141ec'
      );
      const received_data = await response.json();
      this.article_array = received_data.articles;
    },
  },
  created() {
    this.data_fetch();
    this.search_query='';
  },
};
</script>


// Style section ----------------------------------------------------

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

.header_container {
  margin-top: 30px;
  display: flex;
  padding: 10px;
}

.nav_item {
  display: flex;
  flex: 1;
  justify-content: center;
  align-items: center;
}

.logo_img img {
  height: 30px;
  object-fit: contain;
}

.search_container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.search_input{
  position: relative;
  display: flex;
  justify-content: flex-end;
}

input {
  border-radius: 20px;
  padding: 10px;
  width: 250px;
  border: 1px solid rgb(107, 107, 107);
  text-align: center;
}

.search_btn{
  height: 30px;
  width: 30px;
  background-color: rgb(81, 190, 81);
  border-radius: 50%;
  position: absolute;
  margin-top: 6px;
  margin-right: 5px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.arrow{
  color: white;
}
</style>
