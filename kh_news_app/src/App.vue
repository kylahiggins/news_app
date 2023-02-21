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
  flex-direction: column;
}

.heading{
  text-align: center;
}

</style>

<script>
export default {
  data(){ // data itself starts
    return{ // data variables starts
      my_data_array:[]
    } // data variables end
  }, // data itself ends
  methods:{ // funtions are written in methods
    async data_fetch(){
      const response = await fetch("https://newsapi.org/v2/everything?q=music&apiKey=a538540a4b4c4ea48ff8f0b4afb141ec");
      const received_data = await response.json();
      // at this point our data is available under received_data variable
      console.log( received_data );
      this.my_data_array = received_data;
    }
  }, // methods end
  created(){ // created() is where initial code runs once
    this.data_fetch();
  } // end of created
}
</script>