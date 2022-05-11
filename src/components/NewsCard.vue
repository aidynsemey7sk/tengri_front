<template>
    <div class="news-card">
        <div class="news-card__image-container"><img v-bind:src="(pathToImage)" alt=""></div>
        <!-- <img v-bind:src="(pathToImage)" alt="" class="news-card__image-container"> -->
        <span class="news-cart__title">{{title}}</span>
        <ul class="news-cart__data-list">
            <li><time>{{date}}</time></li>
            <li>1352</li>
            <li>7</li>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        title: String,
        id: Number,
        thumbnail: String,
        date: String,

        // isOpen: Boolean,
    },
    data() {
        return {
            pathToImage : this.thumbnail,
        }
    },
    methods: {

    },
    mounted() {
        // console.log(this.thumbnail)
    }
    
}
</script>


<style>
.nw-link {
    background-color: #ffffff;
    height: 100%;
    width: 100%;
}



.news-card {
    /* background-color: #ffffff; */
    height: 100%;
    width: 100%;
    max-height: 271px;
    max-width: 280px;
    min-width: 280px;
    min-height: 271px;
    
}
.news-cart__title{
    display: inline-block;  
    margin-top: 10px;
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 21px;
    letter-spacing: -.01em;
    color: #000000; 
}

.news-cart__data-list {
    max-height: 18px;
    max-width: 285px;
    display: flex;
    margin-top: 10px;
    margin-bottom: 10px;
    vertical-align: baseline;
    font-family: Roboto;
    color: #575757;
}

.news-card__image-container {
    max-height: 160px;
    max-width: 285px;
}

li::after {
    content: "";
    border-radius: 100%;
    width: 2px;
    height: 2px;
    background-color: #575757;
    display: inline-block;
    margin: 0 10px;  
}
</style>