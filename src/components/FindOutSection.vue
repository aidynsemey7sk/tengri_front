<template>
    <section class="tengri-mix tn-container">
            <div class="tn-section-header">
                <a href="#">Узнай</a>

                <ul class="tn-tag-list">
                    <li>#Коронавирус</li>
                    <li>#Новости</li>
                    <li>#Новости Казахстана</li>
                    <li>#Новости мира</li>
                    <li>#Проишествия</li>
                    <li>#Референдум</li>
                </ul>
            </div>


            <div class="article-grid">
                <news-card
                v-for="item in info"
                :key="item"
                :title="item.title"
                :id="item.id"
                :thumbnail="item.get_thumbnail"
                :date="item.date_added"
                :comments_count="item.comments"
              >
              </news-card>
            </div>
        </section>
</template>

<script>
import NewsCard from './NewsCard.vue'
import axios from 'axios'

export default {
    components: {
       'news-card': NewsCard,
    },
    data() {
        return {
            info: [],
        }
    },
    mounted() {
    },
    methods: {
        async loadNews() {
            const response = await axios.get('https://tengrinews.herokuapp.com/')
            
            console.log(response.data)
        }
    },
    created() {

        // axios
        //     .get('http://127.0.0.1:8000/read/')
        //     .then(response => {
        //         console.log(response)
        //         this.info = response.data
        //     })
        //     .catch(err => {
        //         console.log(err)
        //     });

        axios
            .get('https://tengrinews.herokuapp.com/read/')
            .then(response => {
                console.log(response)
                this.info = response.data
            })
            .catch(err => {
                console.log(err)
            });
    }
}
</script>

<style scoped>
.tengri-mix {
    box-sizing: border-box;
    padding: 25px 8px;
    background: #f2f4f5;
}

.tn-container {
    width: 1200px;
}

.tn-section-header {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    margin-bottom: 15px;
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
    z-index: 10;
}

.tn-section-header a {
    text-decoration: none;
    font-family: Roboto;
    font-style: normal;
    font-weight: 700;
    font-size: 40px;
    line-height: 47px;
    letter-spacing: -.02em;
    color: #1b1b1b;
    margin-right: 40px;
    position: relative;
}

.tn-tag-list {
    list-style: none;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    position: relative;
    overflow: hidden;
    overflow-x: auto;
}

.tn-tag-list li {
    margin-right: 10px;
    background: rgba(242,244,245,.1);
    border: 1px solid rgba(11,33,2,.1);
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
    border-radius: 8px;
    padding: 3px 5px;
}

.tn-article-item {
    width: 284px;
    height: 271px;
}



.article-grid {
    display: grid;
    grid-template-columns: 100%;
    grid-gap: 15px;
    grid-template-columns: repeat(4,1fr);

}

.card-image {
    height: 160px;
    width: 284px;
}

.data-list {
    display: flex;
    margin-top: 10px;
    margin-bottom: 10px;
}

.data-list li {
    font-style: normal;
    font-weight: 400;
    font-size: 12px;
    line-height: 14px;
    color: #575757;
}

.tn-article-title {
    margin-top: 10px;
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 18px;
    line-height: 21px;
    letter-spacing: -.02em;
    color: #000000;
    display: block;
}

.data-list li:not(:last-child):after {
    content: "";
    border-radius: 100%;
    width: 2px;
    height: 2px;
    background-color: #575757;
    display: inline-block;
    margin: 0 10px;
}

/* .tn-article-item-banner {
    height: 285px;
    width: 214px;

} */

.item-banner {
    height: 214px;
    width: 285px;
}

.banner-title {
    background-color: #ffffff;
    height: 52px;
    width: 284px;
    margin: 0;
}
</style>