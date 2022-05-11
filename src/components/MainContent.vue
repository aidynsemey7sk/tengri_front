<template>


<div class="main">
  <div class="basic">
  <div class="nw-link-1">
      <div class="top-news">
          <router-link v-bind:to="topNews ? topNews.get_absolute_url : ''">
          <img v-bind:src="(topNews ? topNews.get_image : '')" alt="" class="topNewsImage">
          <h2 class="top-news__title">{{topNews ? topNews.title: ''}}</h2>
          <ul class="top-news__data">
              <li><time>{{topNews ? topNews.date_added : ''}}</time></li>
              <li>3512</li>
              
              <li>114</li>
          </ul>
          

    </router-link>
      </div>
      <!-- <img v-bind:src="topNews" alt="" class="topNewsImage"> -->
  </div>
  <news-card 
  v-for="item in info"
  :key="item"
  :title="item.title"
  :id="item.id"
  :thumbnail="item.get_thumbnail"
  :date="item.date_added"

  ></news-card>

  <!-- <div class="grid-item" v-for="item in news" :key="item">{{item}}</div> -->
</div>

  <div class="rigth-column">
      <div class="rigth-column-banner">
          
      </div>
      <div class="switch">
          <p>переключатель</p>
      </div>
      <div class="rigth-column-news">
          <left-newscard class="card"
          v-for="item in allNews"
            :key="item.id"
            :title="item.title"
          ></left-newscard>

          
      </div>
  </div>
</div>

</template>

<script>
import NewsCard from './NewsCard.vue'
import axios from 'axios'
import LeftNewsCard from './LeftNewsCard.vue'

export default {
    components: {
       'news-card': NewsCard,
       'left-newscard': LeftNewsCard
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
            const response = await axios.get("http://127.0.0.1:8000/kazakhstan_news/britanskii-bloger-rasskazal-chem-zakonchilos/")
            this.topNews = response.data
            console.log('hellow', response.data)

        },
        async loadNews() {
            const response = await axios.get('http://127.0.0.1:8000/')
            
            console.log(response.data)
        }
    },
    created() {

        axios
            .get('http://127.0.0.1:8000/')
            .then(response => {
                console.log(response)
                this.info = response.data
            })
            .catch(err => {
                console.log(err)
            });

        axios
            .get("http://127.0.0.1:8000/kazakhstan_news/britanskii-bloger-rasskazal-chem-zakonchilos/")
            .then(response => {
                console.log(response)
                this.topNews = response.data
            })
            .catch(err => {
                console.log(err)
            })
        
        axios
            .get('http://127.0.0.1:8000/all/')
            .then(response => {
                console.log(response)
                this.allNews = response.data
            })

        


    }
}
</script>


<style>
.main {
    display: flex;
}

.basic {
    width: 900px;
    height: 1074px;

    display: grid;
    /* column-gap: 50px;
    row-gap: 50px; */
    grid-template-columns: auto auto auto;
    place-items: center;
    gap: 20px;
    /* grid-template-columns: 200px auto 100px; */
    grid-template-rows: auto auto auto;
}

.grid-item {
    background-color: #ffffff;
    height: 100%;
    width: 100%;
}


.nw-link-1 {
    grid-column-start: 1;
    grid-column-end: 4;
    grid-row-start: 1;
    grid-row-end: 3;
    background-color: #f2f4f5;
    height: 100%;
    width: 100%;
    min-width: 885px;
    min-height: 502px;
    max-height: 502px;
    max-width: 885px;
}

.rigth-column {
    max-width: 290px;
    display: flex;
    flex-direction: column;
    margin-left: 10px;
    background-color: #ffffff;
}

.rigth-column-banner {
    background-color: #ffffff;
    width: 290px;
    height: 265px;
}

.switch {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 37px;
}

.card {
    max-height: 150px;
    /* height: 150px; */
    width: 269px;
    padding-left: 12px;
    padding-right: 12px;
    /* margin: 0 12px 0 12px; */
    background-color: #ffffff ;
    border-bottom: 1px solid #f2f4f5;
    /* border-style: solid;
    border-color: black;
    border-width: 1px; */
}

.topNewsImage {
    width: 100%;
    height: 100%;
}

.top-news {
    z-index: 0;
    position: relative;
    width: 100%;
}

.top-news__title {
    position: absolute;
    top: 350px;
    left: 0;
    width: 100%;
    color: #ffffff;
    vertical-align: baseline;
    font-family: Roboto;
    font-size: 35px;
    max-width: 715px;
    font-weight: 400;
    margin: 10px 0 0 20px;

}

li::after {
    content: "";
    border-radius: 100%;
    width: 2px;
    height: 2px;
    display: inline-block;
    margin: 0 10px;  
    color: #ffffff;
    font-family: IBM Plex Sans;
    font-size: 12px;
    line-height: 16px;
}

.top-news__data {
    display: flex;
    position: absolute;
    top: 450px;
    left: 0;
    width: 100%;
    color: #ffffff;
    margin: 10px 0 0 20px;
    max-width: 300px;

}


</style>