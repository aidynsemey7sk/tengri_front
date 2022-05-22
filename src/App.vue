<template>
  <div class="tn-main">
    <header-view></header-view>
   <main >
     <router-view class="my-views"/>
   </main>
   <footer-view></footer-view>
  </div>
</template>

<script>
import HeaderView from './views/HeaderView.vue'
import FooterView from './views/FooterView.vue'
export default {
  components: {
    HeaderView,
    FooterView
    
},
  data() {
    return {
    }
  }
}
</script>

<style >


/* body {
  margin: 0;
} */

.tn-main {
  display: flex;
  justify-content: center;
  flex-direction: column;
  background-color: #f2f4f5;
  background-image: url('./assets/optimize.webp');
  display: block;
  height: 100%;
  width: 100%;
        background-repeat: no-repeat;
    background-position: 50% 0px;
    /* image-rendering: auto; */
    background-attachment: fixed;
  margin: 0;
  padding: 0;
}

/* Изменяемый контент */
main {
  display: flex;
  justify-content: center;
  margin: 0;
}

.my-views {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
} 
</style>
