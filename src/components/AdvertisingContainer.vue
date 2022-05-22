<template>
    <div class="adversing">
        <div class="adversing__main">
            <div class="adversin__card"><img src="../assets/banner-1.webp" alt="" class="adversing_image"></div>
            <div class="adversin__card"><img src="../assets/banner-2.webp" alt="" class="adversing_image"></div>
            <div class="adversin__card"><img src="../assets/banner-3.webp" alt="" class="adversing_image"></div>
            <div class="adversin__card"><img src="../assets/banner-4.webp" alt="" class="adversing_image"></div>
        </div>
    </div>
</template>

<style>
.adversing {
    width: 1200px;
    height: 290px;
}

.adversing__main {
    margin: 20px auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-start;

}

.adversing_image {
    width: 290px;
    height: 250px;
}

.adversin__card {
    width: 296px;
    height: 250px;
    background-color: #ffffff;
    width: calc(1/4*100% - 10px);
    margin: 5px;
}
</style>