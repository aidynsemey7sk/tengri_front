<template>
    <div class="post">
                <div class="content">
            <div class="bread-crumbs">
                <ul>
                    <li>Главная</li>
                    <li>Узнай</li>
                    <li>Новости</li>
                    <li>Новости Казахстана</li>
                </ul>
            </div>

            <div class="content__title">
                <h2>{{post.title}}</h2>
            </div>
            <div class="data-list">
                <p>Сегодня</p>
            </div>
            <div class="content__grid">
                <div class="sidebar">
                    <time>Сегодня, 14:45</time>

                    <div class="shared">
                        <ul>
                            <li class="shared__title">Поделиться</li>
                        </ul>

                        <ul class="shared__links">
                            <li><span>Vkontakte</span></li>
                            <li><span>Facebook</span></li>
                            <li><span>Twitter</span></li>
                            <li><span>Однокласники</span></li>
                            <li><span>Telegram</span></li>

                            <span class="shared__count">
                                Новостью поделились: <span class="shared__count" >8</span> человек
                            </span>
                        </ul>

                        <ul class="shared__news">
                            <li class="column-2">Новости</li>
                            <li class="column-2">Новости Казахстана</li>
                            <li class="column-2">Новости Мира</li>
                        </ul>

                    </div>
                </div>

                <div class="news-content">
                    <img v-bind:src="post ? post.get_image : ''" alt="">
                    <article>
                        <p>Среди трех погибших в уличной разборке, которая произошла 7 мая в 
                            Кызылорде, оказался кызылординский спортсмен Куандык Жусип, 
                            передает корреспондент Tengrinews.kz.</p>
                        <p>Казахстанский боксер-профессионал, двукратный серебряный призер 
                            чемпионата мира, действующий "золотой" чемпион мира по версии WBA 
                            Gold Камшыбек Конкабаев, который был знаком с Куандыком 
                            уже несколько лет, подтвердил, что его коллега погиб.</p>
                        <blockquote>
                            <p>"Да, среди погибших в перестрелке, которая произошла 
                            на днях в Кызылорде, к сожалению, оказался и Куандык Жусип. 
                            Мы были знакомы с ним с 2012 года. Не раз вместе тренировались, 
                            ездили на различные сборы по боксу. Очень жаль, что такое случилось", 
                            - сказал известный боксер.</p>
                        </blockquote>
                        <p>
                            Куандык Жусип родился в 1995 году в Жанакорганском районе 
                            Кызылординской области. Он мастер спорта Казахстана по боксу.
                        </p>

                        <p>Как рассказал тренер Сейтжан Токенов, 
                            Куандык подавал большие надежды.</p>

                        <p>"Он был участником различных международных турниров по боксу, 
                            не раз занимал призовые места. К примеру, на последнем международном 
                            турнире, посвященном памяти Абдисамала Нурмаханова, который состоялся в Шымкенте, Куандык занял почетное третье место. Он был неконфликтным человеком, читал намаз, воспитывал троих детей. Недавно устроился охранником на один из городских рынков. 
                            Не знаем, как он попал в эту ситуацию. 
                            Люди выдвигают различные версии, думаем, полиция разберется, 
                            что произошло на самом деле", - добавил он.</p>
                    </article>

                    <div v-for="comment in post.comments"
                    :key="comment.id">
                        {{comment.body}}
                    </div>
                </div>

                <div class="left-banner">
                    <div class="banner">
                        <img src="../assets/x300.webp" alt="">
                        <div class="banner__title">
                            Профессия разработчик на Unity   
                        </div>
                    </div>

                    <div class="left-banne-mix">

                    </div>
                </div>

            </div>
        </div>
    </div>

</template>

<script>
import axios from 'axios'
export default {
    data() {
        return {
            post: Object
        }
    },
    mounted() {
        this.getPost()
    },
    methods: {
        getPost() {
            const category_slug = this.$route.params.category_slug
            const post_slug = this.$route.params.post_slug
            console.log(category_slug, post_slug)

            axios 
                // .get(`http://127.0.0.1:8000/${category_slug}/${post_slug}/`)
                // .then(response => {
                //     this.post = response.data
                // })
                // .catch(err => {
                //     console.log(err)
                // })

            axios 
                .get(`https://tengrinews.herokuapp.com/${category_slug}/${post_slug}/`)
                .then(response => {
                    this.post = response.data
                })
                .catch(err => {
                    console.log(err)
                })
        }
    },
    beforeMount() {
        // this.getPost()
    }
}

</script>

<style scoped>
@import '../../public/post.css';


li {
    list-style-type: none; 
}
.post {
    margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}

.post {
    margin: 0;
    padding: 0;
    border: 0;
    font-size: 100%;
    font: inherit;
    vertical-align: baseline;
}

.content {
    margin: 0;
}

.bread-crumbs {
    height: 24px;
    margin-top: 15px;
    margin-bottom: 25px;
}

.bread-crumbs ul {
    margin-left: 0;
    display: flex;
    justify-content: flex-start

}

.bread-crumbs ul li {
    display: inline-block;
}

.bread-crumbs ul li::after {
    position: relative;
    content: "";
    margin: 0 15px;
    width: 7px;
    height: 10px;
    background: url(../assets/strelka.svg) no-repeat 50%/contain;
    display: inline-block;
}

.content__title {
    max-width: 995px;

    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 48px;
    line-height: 56px;
    max-width: 995px;
    letter-spacing: -.01em;
    color: #2b2b2b;
}

.data-list {
    width: 1200px;
    margin-top: 10px;
    margin-bottom: 10px;
}

.content__grid {
    margin-top: 15px;
    display: grid;
    grid-column-gap: 15px;
    grid-template-columns: 175px 695px 300px;
}

.content__grid time {
    display: block;
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 19px;
    color: var(--gray_1);
    padding-bottom: 10px;
    border-bottom: 2px solid rgba(47,47,47,.12);
}

.shared {
    height: 258px;
    padding: 10px 0;
}

.shared__title {
    text-transform: uppercase;
    font-family: Roboto;
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 19px;
    color: #838383;
}

.shared__links {
    margin-top: 15px;
}

.shared__links li{
    margin-bottom: 15px;
}

span {
    font-family: Roboto;
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 92.58%;
    color: #000000;
}

.news-content img {
    width: 695px;
    height: 450px;
}

article p {
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    color: #000000;
    margin-bottom: 30px;
    margin-top: 15px;
}

blockquote {
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 24px;
    line-height: 32px;
    color: #575757;
    background: #daefe2 url(Group.svg) no-repeat calc(100% - 33px) 50%/72px;
    padding: 25px 125px 25px 15px;
}

.left-banner {
    display: flex;
    flex-direction: column;
}

.banner {
    display: flex;
    flex-direction: column;
    width: 300px;
    height: 265px;
    padding-bottom: 15px;
}

.banner img {
    width: 298px;
    height: 223px;
}

.banner__title {
    width: 298px;
    height: 60px;
    background-color: #2f3b49;

    text-align: center;
    text-transform: uppercase;
    font-family: Roboto;
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 19px;
    color: #ffffff;
}

.left-banne-mix {
    height: 641px;
    background-color: #fbca4a;
}


.shared {
    height: 258px;
    padding: 10px 0;
}

.shared__title {
    text-transform: uppercase;
    font-family: Roboto;
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 19px;
    color: #838383;
}

.shared__news {
    border-bottom: 1px solid #d8d7d7;
    padding: 10px 0;
}

.column-2 {
    align-content: center;
    font-family: Roboto;
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 92.58%;
    color: #000000;
    margin-top: 15px;
}


.shared__links {
    /* margin-top: 15px; */
    border-bottom: 1px solid #d8d7d7;
    padding: 10px 0;
}

.shared__links li{
    margin-bottom: 15px;
    
}

.shared__count {
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 16px;
    color: #838383;
}

span {
    font-family: Roboto;
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 92.58%;
    color: #000000;
}
</style>