<template>
  <div class="content">
    <h2>About</h2>
    <p>LILLYDOO is a ...</p>
  </div>
</template>

<script>
export default {
  name: "About"
};
</script>

<style lang='scss' scoped>
.content {
  min-height: calc(100vh - 214px);
  padding: 0 30px;
  margin: 0 auto;
  overflow: auto;

  h2 {
    font-size: 1.6rem;
    line-height: 1.2;
    text-transform: none;
    margin-bottom: 1rem;
    font-style: normal;
    font-weight: 400;
  }

  p {
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.4;
    margin-bottom: 1rem;
  }
}
</style>