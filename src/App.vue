<template>
  <div id="app">
    <Book/>
    <ScreenshotBtn/>
  </div>
</template>

<script>
import Book from "./components/Book.vue";
import ScreenshotBtn from "./components/ScreenshotBtn.vue";




export default {
  name: "app",
  components: {
    Book,ScreenshotBtn
  }
};
</script>

<style lang="scss">

</style>
