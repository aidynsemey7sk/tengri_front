<template>
  <div class="home">
    <SubContainer />
    <MainContent />
    <AdvertisingContainer />
    <ReadSection />

  </div>
</template>

<script>
import SubContainer from '../components/SubContainer.vue'
import MainContent from '../components/MainContent.vue'
import AdvertisingContainer from '../components/AdvertisingContainer.vue'
import ReadSection from '../components/ReadSection.vue'

export default {
  name: 'Home',
  components: {
    SubContainer, MainContent, 
    AdvertisingContainer, ReadSection
  }
}
</script>

<style>
</style>
