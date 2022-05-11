<template>
  <div class="main-page">
   <FixedMenu />
   <router-view/>
  </div>
</template>

<script>
import FixedMenu from './components/FixedMenu.vue'
export default {
  components: {
    FixedMenu
  },
  data() {
    return {
    }
  }
}
</script>

<style>

body {
  margin: 0;
}

.main-page {
  display: flex;
  justify-content: center;
  background-color: #f2f4f5;
}
</style>
