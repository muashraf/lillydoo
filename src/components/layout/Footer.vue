<template>
  <footer>© 2020 LILLYDOO GmbH</footer>
</template>

<script>
export default {
  name: "Footer"
};
</script>

<style lang='scss' scoped>
footer {
  @include set-background($primary-color);
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 400;
  line-height: 1.4;
}
</style>