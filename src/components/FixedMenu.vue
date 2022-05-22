<template>
<header>
   <div class="navbar">
       <!-- Верхняя часть навбара -->
      <div class="nav-item-top">
          
         <div class="flip-left">
            <ul class="flip-left-list">
               <li class="my-li">TengriMix</li>
               <li class="my-li">TengriTv</li>
               <li class="my-li">TengriTravel</li>
               <li class="my-li">Победители</li>
               <li class="my-li">Законы Казахстана</li>
               <li class="my-li">Спецпроекты</li>
               <div class="course-list">
                    <ul>
                        <li><span class="course"><i class="icon-dollar"></i></span>442.44</li>
                        <li><span class="course"><i class="icon-euro"></i></span>467.44</li>
                        <li><span class="course"><i class="icon-rouble"></i></span>6.74</li>
                    </ul>
                </div>
            </ul>
         </div>
      </div>
      <!-- Нижняя часть навбара -->
      <div class="nav-item-bottom">
         <div class="nav-item-bottom__container">
            <a href="/"><img src="../assets/tengri-logo.png" alt=""></a>
            <div class="adult-block"></div>
            <div class="type-materials">
               <ul class="li-materials">
                  <li><a href="">УЗНАЙ</a></li>
                  <li><a href="">ПОЧИТАЙ</a></li>
                  <li><a href="">ПОСМОТРИ</a></li>
               </ul>
            </div>
            <div class="weather">+15 &#176C</div>
            <div class="language-switcher">Казакша</div>
            <div class="nav-item">Search</div>
            <div class="subscribe-whatsapp">
               <div>
                  <p>Присылайте свои новости на</p>
                  <span>WhatsApp +7(777) 001 44 99</span>
               </div>
            </div>
         </div>
      </div>
   </div>
</header>    
</template>


<style>

li {
    list-style-type: none; 
}

header {
    width: 1833px;
    height: 120px;
    /* background-color: #f2f4f5; */
    display: flex;
    justify-content: center;
    z-index: 999;
}
/* Верхняя часть навбара */
.navbar {
    height: 106px;
    width: 1200px;
    position: fixed;
    background-color: #f2f4f5;
    z-index: 999;
}

.nav-item-top {
    background-color: #757575;
    height: 43.99px;
    display: flex;
    align-items: center;
}

.flip-left {
    padding: 10px;
    display: flex;
}

.flip-left-list {
    display: flex;
}

.my-li {
    cursor: pointer;
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 16px;
    color: #FFFFFF;
    text-decoration: none;
    margin-right: 20px;
}

.flip-rigth {
    display: flex;
}

.course-container ul{
    display: flex;
    color: #ffffff;
}

.course-container{
    margin-left: 255px;
}


/* Курсы валют  */
.course-list {
    margin-left: 320px;
    width: 250px;
    display: flex;
    justify-content: space-around;
}

.course-list ul{
    display: flex;
    color: #FFFFFF;
    justify-content: space-between;
}



.my-li a {
    cursor: pointer;
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 16px;
    color: #FFFFFF;
    text-decoration: none;
    margin-right: 20px;
}

.icon-dollar {
    background-image: url(dollar-white.svg);
    background: no-repeat 50%/contain;
    width: 15px;
    height: 15px;
    display: inline-block;
}

.icon-euro {
    background-image: url(euro-white.svg);
    background: no-repeat 50%/contain;
    width: 15px;
    height: 15px;
    display: inline-block;
}

.icon-rouble {
    background-image: url(rubl-white.svg);
    background: no-repeat 50%/contain;
    width: 15px;
    height: 15px;
    display: inline-block;
}

.course-list ul li span .icon-dollar{
    background-image: url(dollar-white.svg);
}
.course-list ul li span .icon-euro{
    background-image: url(euro-white.svg);
}
.course-list ul li span .icon-rouble{
    background-image: url(rubl-white.svg);
}

.course-list ul li{
    font-family: 'Roboto', sans-serif;
    font-style: normal;
    font-weight: 300;
    font-size: 14px;
    line-height: 16px;
    color: #FFFFFF;
    text-decoration: none;
    display: inline-flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    margin-left: 15px;
}

/* nav-item-bottom нижняя часть навбара */
.nav-item-bottom {
    display: flex;
    justify-content: center;
    background-color: #ffffff;
    height: 62px;
}

img {
    vertical-align: middle;
}

.nav-item-bottom__container {
    height: inherit;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
}
.nav-item-bottom__container a{
    margin-left: 5px;
}

.li-materials {
    list-style-type: none;
    padding-left: -0;
    margin-bottom: 0;
}

.li-materials li{
    display: inline-block;
}

.li-materials a{
    
    text-decoration: none;
    display: inline-block;
    font-family: Roboto;
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 19px;
    text-transform: uppercase;
    color: #2f2f2f;
}

.li-materials a::before{
    position: relative;
    content: "";
    height: 20px;
    width: 2px;
    background-color: #575757;
    display: inline-block;
    margin: 0 10px;
}

.type-materials {
    display: flex;
    flex-flow: row nowrap   ;
}

.subscribe-whatsapp {
    background-color: #32a801;
    height: 62px;
    width: 240px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.subscribe-whatsapp p {
    color: #ffffff;
}

.subscribe-whatsapp span {
    color: #ffffff;
}

.adult-block {
    background: url(../assets/tn-18.svg) no-repeat 50%/contain;
    width: 50px;
    height: 50px;
    margin: 7px 0 5px;
}

.weather {
    font-family: Roboto;
    font-style: normal;
    font-weight: 700;
    font-size: 14px;
    line-height: 16px;
    color: #2b2b2b;
}

.language-switcher {
    font-family: Roboto;
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 16px;
    color: #3dc704;
}
</style>