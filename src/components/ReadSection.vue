<template>
    <div class="news">
        <div class="read-container">
            <div class="read-title">
                <h3>Почитай</h3>
                <ul>
                    <li>#Спорт</li>
                    <li>#Здоровье</li>
                    <li>#Красота</li>
                    <li>#Красота</li>
                    <li>#Красота</li>
                    <li>#Красота</li>
                    <li>#Красота</li>
                    <li>#Красота</li>
                    <li>#Красота</li>
                </ul>
            </div>

            <div class="news__main">
            <news-card  class="adversin__card"
                v-for="item in info"
                :key="item"
                :title="item.title"
                :id="item.id"
                :thumbnail="item.get_thumbnail"
                :date="item.date_added"
            >
            </news-card>
        </div>
        </div>
        
    </div>
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
            const response = await axios.get('http://127.0.0.1:8000/')
            
            console.log(response.data)
        }
    },
    created() {

        axios
            .get('http://127.0.0.1:8000/read/')
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

.read-container {
    background-color: #dbf5d0;
}
.news {
    width: 1200px;
    height: 290px;
}

.news__main {
    margin: 20px auto;
    display: flex;
    flex-wrap: wrap;
    justify-content: flex-start;
    background-color: #dbf5d0;

}

.adversin__card {
    width: 284px;
    height: 250px;
    background-color: #dbf5d0;
    width: calc(1/4*100% - 10px);
    margin: 7px;
}

h3 {
    font-family: Roboto;
    font-style: normal;
    font-weight: 700;
    font-size: 40px;
    line-height: 47px;
    letter-spacing: -.02em;
    color: #1b1b1b;
    margin-right: 40px;
    position: relative;
    width: 200px;
}

.read-title {
    display: flex;
}
ul {
    display: flex;
    align-items: center;
    margin: auto;
    
}
li {
    border: 1px solid #1b1b1b;
}

</style>