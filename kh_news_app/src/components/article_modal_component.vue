<script setup>
defineProps({
  modal_obj: {
    type: Object,
    required: true,
  },
});
</script>

<template>

  <div class="article_modal_container">
    <div class="article_image_wrapper">
      <img :src="modal_obj.urlToImage" alt="" />
    </div>

    <div class="article_title">
        <p>{{ modal_obj.title }}</p>
      </div>


    <div class="row">

        <div class="article_author">
        <p>AUTHOR: {{ modal_obj.author }}</p>
      </div>


      <div class="time_date">
        <p>{{ modal_obj.publishedAt }}</p>
      </div>

    </div>

    <div class="content_container">
      <p>{{ modal_obj.content }}</p>
      <p>Go to Article: {{ modal_obj.url }}</p>
    </div>
  </div>
  
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700&display=swap");
.article_modal_container {
  display: flex;
  background-color: white;
  position: absolute;
  flex-direction: column;
  padding: 10px;
}

.article_image_wrapper {
  display: flex;
}

img {
  height: 100%;
  width: 100%;
  object-fit: cover;
  border-radius: 10px;
}

.article_author {
  font-size: 12px;
}

.time_date {
  font-size: 10px;
  font-weight: 100;
}

.content_container{
    font-size: 12px;
}

.row{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
}
</style>
