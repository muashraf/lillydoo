<template>
  <img v-bind:src="url" />
</template>

<script>
export default {
  name: "DiaperImg",
  props: ["url"]
};
</script>

<style scoped>
</style>