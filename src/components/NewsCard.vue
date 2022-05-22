<template>
    <div class="news-card">
        <router-link v-bind:to="get_absolute_url ? get_absolute_url : ''" class="my-link">
        <div class="news-card__image-container"><img v-bind:src="(pathToImage)" alt=""></div>
        <span class="news-cart__title">{{title}}</span>
        <!-- <div class="data-list">
            <ul class="my-ul">
                <li class="my-li">{{date}}</li>
                <li class="my-li">
                    <i class="eye"></i><span class="my-span">{{views}}</span>
                </li>
                <li class="my-li">
                    <i class="comments"></i><span>{{comments_count.length}}</span>
                </li>
            </ul>
        </div> -->
        <ul class="data">
         <li>{{date}}</li>
         <li><span class="icon_eye"></span><span class="data-info">{{views}}</span></li>
         <!-- <li><span class="icon_comments"></span><span class="data-info">{{comments_count.length}}</span></li> -->
        </ul>
        </router-link>
    </div>
</template>

<script>
export default {
    props: {
        title: String,
        id: Number,
        thumbnail: String,
        date: String,
        get_absolute_url: String,
        views: Number,
        comments_count: Array,
    },
    data() {
        return {
            pathToImage : this.thumbnail,
        }
    },
    methods: {

    },
}
</script>


<style scoped>

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

.news-card__image-container {
    max-height: 160px;
    max-width: 285px;
}

.data-list {
    max-height: 18px;
    max-width: 285px;
    margin-top: 10px;
    margin-bottom: 10px;
    vertical-align: baseline;
    font-family: Roboto;
    color: #575757;
}

.my-ul {
    /* margin:auto; */
    display: flex;
    
}

.my-li {
    /* display:table-cell; */
    align-items: center;
    justify-content: center;
}

.eye {
    background-image: url('../assets/eye-dark.svg');
}

.eye {
    width: 17px;
    height: 14px;
    margin: 0 5px 0 0;
    display: inline-block;
}

.my-span {
    vertical-align: center;
}

.comments {
    background-image: url('../assets/comment-dark.svg');
}

.comments {
    width: 15px;
    height: 14px;
    margin: 0 5px -5px 0;
    display: inline-block;
}

.my-link {
    text-decoration: none;
}

.data {
    margin: 10px 0 10px 0;
    margin-top: 10px;
    display: flex;
    flex-direction: row;
    color: #575757;
    font-size: 14px;
    justify-content: flex-start;
    height: 20px;
}

.data li {
    display: flex;
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 14px;
    margin-right: 15px;
}

.icon_eye {
        position: relative;
        display: inline-block;
        width: 12px;
        height: 12px;
        background-image: url('../assets/eye-dark.svg');
        background-size: 12px;
        background-repeat: no-repeat;
        /* margin-top: 2px; */
        margin-right: 3px;
    }

.icon_comments {
        position: relative;
        display: inline-block;
        width: 12px;
        height: 12px;
        background-image: url('../assets/comment-dark.svg');
        background-size: 12px;
        background-repeat: no-repeat;
        /* margin-top: 2px; */
        margin-right: 3px;
    }

.data-info {
    font-size: 14px;
}
</style>