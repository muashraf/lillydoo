<template>
  <form @submit.prevent="addToCart">
    <input type="hidden" v-model="this.diaper" name="diaper" />
    <input type="submit" value="Add to Cart" class="btn-primary" />
  </form>
</template>

<script>
export default {
  name: "AddToCart",
  props: ["diaper"],
  methods: {
    addToCart() {
      const { name, weight } = this.diaper;
      alert(`Diaper ${name} with ${weight} has been added to the cart.`);
    }
  }
};
</script>

<style lang='scss' scoped>
.btn-primary {
  @extend %btn;
  @include set-background(lighten($primary-color, 10%));
}
</style>