<script setup>defineProps({ 
    article_obj: { 
      type: Object, 
      required: true
    }
  }); 
  </script>

<template>

    <div class="article_container">

        <div class="article_image_wrapper">
            <img :src="article_obj.urlToImage" alt=""></div>

        <div class="article_text_wrapper">
            <div class="author">
                <p>AUTHOR: {{ article_obj.author }}</p>
            </div>
            <div class="article_title">
                <p>{{ article_obj.title }}</p>
            </div>
            <div class="time_date">
                <p>{{ article_obj.publishedAt }}</p>
            </div>
        </div>
    </div>

</template>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700&display=swap');

.article_container{
    margin-top: 10px;
    display: flex;
    flex-direction: row;
    gap: 20px;
    padding: 10px;
    box-shadow: 0px 0px 15px 0px rgb(0 0 0 / 9%);
    border-radius: 10px;
}

.article_image_wrapper{
    display: flex;
    max-width: 150px;
    min-width: 150px;
}

img{
    height: 100%;
    width: 100%;
    object-fit: cover;
    border-radius: 10px;
}

.article_text_wrapper{
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
}

.author{
    font-size: 12px;
}

.article_title{
    font-family: 'poppins' sans-serif;
    font-size: 1em;
    font-weight: 400;
}

.time_date{
    font-size: 10px;
    font-weight: 100;
}
</style>