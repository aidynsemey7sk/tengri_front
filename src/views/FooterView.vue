<template>
    <footer>
        <div class="tn-container">
            <div class="footer-grid">
                <div>
                    <ul class="data-list">
                        <li><a href="">О проекте</a></li>
                        <li><a href="">Погода в Казахстане</a></li>
                        <li><a href="">Реклама</a></li>
                        <li><a href="">Пресс-релизы</a></li>
                        <li><a href="">Карта сайта</a></li>
                    </ul>

                    <a href="" class="copyright-warning">
                        Информация об ограничениях использования материалов Tengrinews.kz
                    </a>
                    <br>
                    <br>
                    <a href="" class="copyright-warning">
                        Политика конфиденциальности Tengrinews.kz
                    </a>
                </div>
                <label>Тема</label>
                <div><ul>
                    <li>Редакция:</li>
                    <li>+7(777) 001 44 99</li>
                    <li>Реклама:</li>
                    <li>+7(700) 3 888 109</li>
                </ul></div>
                <div>Мы в социальных сетях</div>
            </div>
        </div>

        <!-- Города -->
        <div class="list-grid-container">
        <ul class="list-grid">
            <li>Новости Алматы</li>
            <li>Новости Нур-Султана</li>
            <li>Новости Шымкента</li>
            <li>Новости Караганды</li>
            <li>Новости Актобе</li>
            <li>Новости Усть-Каменогорска</li>
            <li>Новости Уральска</li>
            <li>Новости Костаная</li>
            <li>Новости Кызылорды</li>
            <li>Новости Атырау</li>
            <li>Новости Актау</li>
            <li>Новости США</li>
            <li>Новости России</li>
            <li>Новости Украины</li>
            <li>Новости ЕАЭС</li>
            <li>Новости Узбекистана</li>
            <li>Энергетика</li>
            <li>Преступность</li>
            <li>События</li>
            <li>Чрезвычайные проишествия</li>
            <li>Катастрофы</li>
            <li>Футбол</li>
            <li>Теннис</li>
            <li>Киберспорт</li>
            <li>Бокс</li>
            <li>Хоккей</li>
            <li>Политика</li>
            <li>Авто</li>
        </ul>
        </div>

        <hr>

        <div class="tn-footer-grid-meta">
            <span class="tn-copyright">© 2008-2022 ТОО «EML»</span>

            <ul class="tn-list-app">
                <li></li>
                <li></li>
                <li></li>
                <li></li>
            </ul>

            <span class="tn-designer">
                "Designed by "
                <b>ibec systems</b>
            </span>
        </div>
    </footer>
</template>
<style scoped>
footer {
    display: flex;
    flex-direction: column;
    align-items: center;
    box-sizing: border-box;
    background: linear-gradient(180deg,#eaeaeb 0,#eaeaeb 3%,#ffffff 8%,#ffffff);
    box-shadow: 0 17px 24px rgba(0,0,0,0.1);
    margin-top: 150px;
}

.tn-container {
    box-sizing: border-box;
    padding: 25px 8px;
    width: 1200px;
}

.footer-grid {
    width: 100%;
    display: flex;
    grid-gap: 30px;
    grid-template-columns: auto 90px 135px 205px;
    
}

.tn-footer-grid {
    display: grid;
    grid-gap: 25px;
    grid-template-columns: 1fr;
    -webkit-box-align: baseline;
    -ms-flex-align: baseline;
    align-items: baseline;
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

.data-list li:not(:last-child):after {
    content: "";
    border-radius: 100%;
    width: 2px;
    height: 2px;
    background-color: #575757;
    display: inline-block;
    margin: 0 10px;
}

footer .data-list li a, footer .tn-designer {
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
}

footer .data-list li a {
    font-family: Roboto;
    line-height: 16px;
    color: #000000;
}

.contact-list li>*, .copyright-warning {
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 16px;
    color: #000000;
}

.list-grid {
    display: grid;
    grid-template-columns: repeat(4,1fr);
    margin: 15px auto;
    grid-gap: 5px;
}

.list-grid-container {
    width: 1200px;
}

footer hr {
    border-top: 1px solid #ccc;
    background: transparent;
    color: transparent;
}

hr {
    display: block;
    unicode-bidi: isolate;
    margin-block-start: 0.5em;
    margin-block-end: 0.5em;
    margin-inline-start: auto;
    margin-inline-end: auto;
    overflow: hidden;
    border-style: inset;
    border-width: 1px;
}

</style>