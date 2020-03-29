<template>
  <ul class="diaper-size">
    <li
      v-bind:key="diaper.id"
      v-for="diaper in diapers"
      v-on:click="selectDiaper(diaper)"
      v-bind:id="diaper.id"
    >
      {{diaper.name}}
      <br />
      <span>{{diaper.weight}}</span>
    </li>
  </ul>
</template>

<script>
export default {
  name: "Diaper",
  props: ["diapers"],
  data() {
    return {
      diaper: {}
    };
  },
  methods: {
    selectDiaper(diaper) {
      let x = document.getElementById(this.diaper.id);
      x.classList.remove("active");
      let y = document.getElementById(diaper.id);
      y.classList.add("active");
      this.$emit("diaper-selection", diaper);
      this.diaper = diaper;
    }
  },
  mounted() {
    let x = document.getElementById(this.diapers[0].id);
    x.classList.add("active");
    this.diaper = this.diapers[0];
  }
};
</script>

<style lang='scss' scoped>
ul {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 0 !important;
  display: flex;
  list-style-type: none;

  li {
    @extend %btn;
    color: #7c7c7c;
    border: 1px solid #7c7c7c;
    border-radius: 0px;
    width: 100px;
    height: 55px;
    margin: 0;
    padding: 5px;
    text-align: center;
    margin-bottom: 1rem;
    font-size: 1rem;
    font-weight: 600;

    span {
      font-size: 0.8rem;
      font-weight: normal;
    }
  }

  li.active {
    @include set-background(lighten($primary-color, 10%));
    cursor: pointer;
  }

  li:hover {
    @include set-background(lighten($primary-color, 10%));
    cursor: pointer;
  }
}

@media (max-width: 700px) {
  ul {
    flex-wrap: wrap;
    justify-content: flex-start;

    li {
      margin-right: 0.5rem;
    }
  }
}
</style>