<template>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />

    <div class="header_container">
        <div class="nav_item">
            <span class="material-symbols-outlined">menu</span>
        </div>

        <div class="nav_item">
            <div class="logo_img">
                <img src="../assets/images/Asset 1.png" alt="news icon">
            </div>
        </div>

        <div class="nav_item" @click="search_click = !search_click;">
            <span class="material-symbols-outlined">search</span>
        </div>
    </div>


<div v-if="search_click" class="search_container">
        <div class="search_input">
            <input type="text" placeholder="Search">
        </div>
    </div>


    
    
</template>

<style scoped>
.header_container{
    margin-top: 30px;
    display: flex;
    padding: 10px;
}

.nav_item{
    display: flex;
    flex: 1;
    justify-content: center;
    align-items: center;
}

.logo_img img{
    height: 30px;
    object-fit: contain;
}

.search_container{
    display: flex;
    justify-content: center;
    align-items: center;
}

input{
    border-radius: 20px;
    padding: 10px;
    width: 250px;
    border: 1px solid rgb(107, 107, 107);
    text-align: center;
}
</style>

<script>
export default {
  data(){ // data itself starts
    return{ // data variables starts
    search_click : true
    } // data variables end
  }, // data itself ends
  }
</script>


