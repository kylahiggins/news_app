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
            <img src="" alt=""></div>

        <div class="article_text_wrapper">
            <div class="author">
                <p>{{ article_obj.author }}</p>
            </div>
            <div class="article_title">
                <h3>{{ article_obj.title }}</h3>
            </div>
            <div class="time_date">
                <p>{{ article_obj.publishedAt }}</p>
            </div>
        </div>
    </div>

</template>

<style scoped>

.article_container{
    margin-top: 10px;
    display: flex;
    flex-direction: row;
    gap: 30px;
    padding: 10px;
    box-shadow: 0px 0px 15px 0px rgb(0 0 0 / 9%);
    border-radius: 10px;
}

.article_image_wrapper{
    display: flex;
    max-width: 150px;
}

img{
    height: 100%;
    width: 100%;
    object-fit: contain;
    border-radius: 10px;
}

.article_text_wrapper{
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
}

.author{
    font-size: 10px;
}

.article_title{
    font-size: 1.2em;
    font-weight: 600;
}

.time_date{
    font-size: 10px;
    font-weight: 100;
}


</style>