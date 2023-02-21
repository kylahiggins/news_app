<template>

    <div class="article_container">

        <div class="article_image_wrapper">
            <img src="https://images.unsplash.com/photo-1474511320723-9a56873867b5?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8YW5pbWFsfGVufDB8fDB8fA%3D%3D&w=1000&q=80" alt="">
        </div>

        <div class="article_text_wrapper">
            <div class="author">author</div>
            <div class="article_title">title</div>
            <div class="time_date">date and time</div>
        </div>
    </div>

</template>

<script>
export default {

}
</script>

<style scoped>

.article_container{
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
    justify-content: center;
}


</style>