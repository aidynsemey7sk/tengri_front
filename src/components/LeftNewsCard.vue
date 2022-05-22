<template>
    <div class="title-block">
        <router-link v-bind:to="get_absolute_url ? get_absolute_url : ''" class="my-link">
        <span>{{title}}</span>
        </router-link>
        <ul class="data">
         <li>{{date}}</li>
         <li><span class="icon_eye"></span><span class="data-info">{{views}}</span></li>
         <!-- <li><span class="icon_comments"></span><span class="data-info">{{comments_count.length}}</span></li> -->
        </ul>
    </div>
    
</template>


<script>
export default {
    props: {
        title: String,
        get_absolute_url: String,
        date: String,
        views: Number,
        comments_count: Array,

    },
    data() {
        return {

        }
    }

}
</script>

<style scoped>

.title-block {
    padding: 12px 0;
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 131.25%;
    color: #2b2b2b;
    border-bottom: 1px solid rgba(0,0,0,0.1);
    margin: 0 12px 0 12px;

}

.data {
    margin: 10px 0 10px 0;
    margin-top: 10px;
    display: flex;
    flex-direction: row;
    color: #575757;
    font-size: 12px;
    justify-content: flex-start;
}

.data li {
    display: flex;
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 14px;
    margin-right: 15px;
}

.my-link {
    text-decoration: none;
    color: #2b2b2b;
    
}

.icon_eye {
        position: relative;
        display: inline-block;
        width: 14px;
        height: 14px;
        background-image: url('../assets/eye-dark.svg');
        background-size: 14px;
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
        margin-top: 2px;
        margin-right: 3px;
    }

.data-info {
    font-size: 14px;
}

</style>