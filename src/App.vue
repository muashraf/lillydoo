<template>
  <div id="app">
    <Header />
    <div class="row">
      <router-view />
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import Footer from "./components/layout/Footer";
export default {
  name: "app",
  components: {
    Header,
    Footer
  }
};
</script>

<style lang='scss'>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: $font-stack;
  line-height: 1.4;
}

.row {
  padding: 2rem 0 2rem 0;
  margin: 0 auto;
  max-width: 100rem;
  width: 100%;
}
</style>
