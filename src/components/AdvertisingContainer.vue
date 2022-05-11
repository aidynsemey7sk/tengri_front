<template>
    <div class="adversing">
        <div class="adversing__main">
            <div class="adversin__card"></div>
            <div class="adversin__card"></div>
            <div class="adversin__card"></div>
            <div class="adversin__card"></div>
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

.adversin__card {
    width: 296px;
    height: 250px;
    background-color: #ffffff;
    width: calc(1/4*100% - 10px);
    margin: 5px;
}
</style>