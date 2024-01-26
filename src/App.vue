
<template>
  <Banner />
  <MainContent />
  
</template>

<script lang="ts">
import Banner from "./components/Banner.vue";
import MainContent from './components/MainContent.vue';

  export default {
    name: "App",
    components: {
      Banner,
      MainContent
    }
}
</script>

<style scoped>
</style>
