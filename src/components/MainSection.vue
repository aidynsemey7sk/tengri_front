<template>
<section class="main-section">
    <div class="main-container">
        <div class="news-container sub-container">
            <div class="news-container">
                <!-- центральная сетка -->
                <div class="news-container-grid">
                    <div class="news-item top-news">
                        <router-link v-bind:to="topNews ? topNews.get_absolute_url : ''">
                        <picture>
                            <img v-bind:src="(topNews ? topNews.get_image : '')" alt="" class="top-news-image">
                       </picture>

                        <div>
                            <h2 class="top-news__title">{{topNews ? topNews.title: ''}}</h2>
                        </div>

                        <ul class="top-news__data">
                            <li><time>{{topNews ? topNews.get_date : ''}}</time></li>
                            <li>{{topNews ? topNews.view_count : ''}}</li>
                            <!-- <li>{{topNews ? topNews.comments.length : ''}}</li> -->
                        </ul>


                        </router-link>
                    </div>

                    <news-card 
                      v-for="item in info"
                      :key="item"
                      :title="item.title"
                      :id="item.id"
                      :thumbnail="item.get_thumbnail"
                      :date="item.get_date"
                      :get_absolute_url="item.get_absolute_url"
                      :views="item.view_count"
                      :comments_count="item.comments"
                    >
                    </news-card>
                </div>
            </div>

            <!-- Правый столбик новостей -->
            <div class="rigth-column-news">
                <div class="rigth-column-banner">
                <img src="../assets/main-banner.png" alt="">
                </div>
                

                <!-- Необходимо сделать кнопку переключателя  -->
                <div class="switch-container">
                    <div class="onoffswitch"></div>
                    <label for="" class="onoffswitch-label">Популярное</label>
                </div>

                <left-newscard class="card"
                  v-for="item in allNews"
                  :key="item.id"
                  :title="item.title"
                  :get_absolute_url="item.get_absolute_url"
                  :date="item.get_date"
                  :views="item.view_count"
                  :comments_count="item.comments"
                ></left-newscard>
            </div>
        </div>

        <advertising-container></advertising-container>
        <read-section></read-section>
        <find-out-section></find-out-section>
        <tengri-mix></tengri-mix>
        

    </div>
</section>
</template>

<style>
    
    .main {
        display: flex;
        justify-content: center;
        background-color: #f2f4f5;
    }

    .main-container {
        width: 1200px;
    }

    /* Делим на две колонки большую и маленькую */
    .news-container {
        display: grid;
        grid-template-columns: 885px 300px;
        grid-gap: 15px;
    }

    /* Центральная сетка */
    .news-container-grid {
        display: grid;
        grid-template-columns: repeat(3,1fr);
        grid-gap: 15px;
        grid-column-gap: 15px;
    }

    /* Главная новость */
.top-news {
    grid-column: span 3;
    height: 502px;
    width: 100%;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
}

.top-news-image{
    /* position: relative; */
    width: 100%;
    height: 100%;
    z-index: 0;
}

.top-news__title {
    position: absolute;
    top: 640px;
    left: 320px;
    width: 100%;
    color: #ffffff;
    vertical-align: baseline;
    font-family: Roboto;
    font-size: 35px;
    max-width: 715px;
    font-weight: 400;
    margin: 10px 0 0 20px;
}

.top-news__data {
    display: flex;
    position: absolute;
    top: 725px;
    left: 320px;
    width: 100%;
    color: #ffffff;
    margin: 10px 0 0 20px;
    max-width: 300px;
}

.top-news__data li{
    margin-right: 35px;
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 14px;
    color: #ffffff;
}

.top-news__data li:not(:last-child):after {
    content: "";
    border-radius: 100%;
    background-color: #ffffff;
    width: 2px;
    height: 2px;
    display: inline-block;
    margin: 0 10px;
    font-size: 12px;
    line-height: 16px;
}

/* Правая колонка  */

.rigth-column-news {
    background-color: #ffffff;
    height: 1074px;
     overflow: auto;
}

/* Необходимо сделать кнопку переключателя */
.switch-container {
    height: 30px;
    padding: 8px 15px;
}


</style>

<script>
import NewsCard from './NewsCard.vue'
import axios from 'axios'
import LeftNewsCard from './LeftNewsCard.vue'
import AdvertisingContainer from '../components/AdvertisingContainer.vue'
import ReadSection from '../components/ReadSection.vue'
import FindOutSection from '../components/FindOutSection.vue'
import TengriMix from './TengriMix.vue'

export default {
    components: {
       'news-card': NewsCard,
       'left-newscard': LeftNewsCard,
       'advertising-container': AdvertisingContainer,
       'read-section': ReadSection,
       'find-out-section': FindOutSection,
       'tengri-mix': TengriMix,
    },
    data() {
        return {
            info: [],
            topNews: null,
            allNews: [],
        }
    },
    mounted() {
    },
    methods: {

        async loadTopNews() {
            const response = await axios.get("https://tengrinews.herokuapp.com/kazakhstan_news/britanskii-bloger-rasskazal-chem-zakonchilos/")
            this.topNews = response.data
            console.log('hellow', response.data)

        },
        async loadNews() {
            const response = await axios.get('https://tengrinews.herokuapp.com/')
            
            console.log(response.data)
        },


        // async loadTopNews() {
        //     const response = await axios.get("http://127.0.0.1:8000/kazakhstan_news/britanskii-bloger-rasskazal-chem-zakonchilos/")
        //     this.topNews = response.data
        //     console.log('hellow', response.data)

        // },
        // async loadNews() {
        //     const response = await axios.get('http://127.0.0.1:8000/')
            
        //     console.log(response.data)
        // }
    },
    created() {

        // axios
        //     .get('http://127.0.0.1:8000/')
        //     .then(response => {
        //         console.log(response)
        //         this.info = response.data
        //     })
        //     .catch(err => {
        //         console.log(err)
        //     });

        // axios
        //     .get("http://127.0.0.1:8000/top/")
        //     .then(response => {
        //         console.log(response)
        //         this.topNews = response.data
        //     })
        //     .catch(err => {
        //         console.log(err)
        //     })
        
        // axios
        //     .get('http://127.0.0.1:8000/all/')
        //     .then(response => {
        //         console.log(response)
        //         this.allNews = response.data
        //     })

        axios
            .get('https://tengrinews.herokuapp.com/')
            .then(response => {
                console.log(response)
                this.info = response.data
            })
            .catch(err => {
                console.log(err)
            });

        axios
            .get("https://tengrinews.herokuapp.com/top/")
            .then(response => {
                console.log(response)
                this.topNews = response.data
            })
            .catch(err => {
                console.log(err)
            })
        
        axios
            .get('https://tengrinews.herokuapp.com/all/')
            .then(response => {
                console.log(response)
                this.allNews = response.data
            })
    }
}
</script>