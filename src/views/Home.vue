<template>
  <main-section></main-section>

  <!-- <div class="home">

    
    



    <MainContent />
    <AdvertisingContainer />
    <ReadSection />
  </div> -->
</template>

<script>
import SubContainer from '../components/SubContainer.vue'
import MainContent from '../components/MainContent.vue'
import AdvertisingContainer from '../components/AdvertisingContainer.vue'
import ReadSection from '../components/ReadSection.vue'
import MainSection from '../components/MainSection.vue'

export default {
  name: 'Home',
  components: {
    SubContainer, MainContent, 
    AdvertisingContainer, ReadSection, MainSection
    
  }
}
</script>

<style scoped>




.home {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
