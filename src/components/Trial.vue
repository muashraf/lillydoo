<template>
  <div class="content">
    <div class="diaper-img">
      <DiaperImg v-bind:url="diaper.img" />
    </div>
    <div class="diaper-showcase">
      <h2>Discover our skin friendliness</h2>
      <div>
        <p class="uppercase">Choose your size</p>
        <Diaper v-bind:diapers="diapers" v-on:diaper-selection="changeDiaperImg" />
      </div>
      <p>Now test our skin-friendly diapers and receive our wet wipes with 99% water in sizes 1 - 3 or the sensitive wet wipes in sizes 4 - 5.</p>
      <ul>
        <li>We pay for the products, you only pay for the shipping.</li>
        <li>Automatic transition to diaper subscription that can be canceled at any time for € 49.50 per delivery.</li>
        <li>Prices include VAT, plus shipping costs if applicable</li>
      </ul>
      <AddToCart v-bind:diaper="diaper" />
    </div>
  </div>
</template>

<script>
import DiaperImg from "./DiaperImg";
import Diaper from "./Diaper";
import AddToCart from "./AddToCart";

export default {
  name: "Trial",
  components: { DiaperImg, Diaper, AddToCart },
  data() {
    return {
      diaper: this.diapers[0]
    };
  },
  props: ["diapers"],
  methods: {
    changeDiaperImg(diaper) {
      this.diaper = diaper;
    }
  }
};
</script>

<style lang='scss' scoped>
.content {
  min-height: calc(100vh - 214px);
  padding: 0 30px;
  display: flex;
  align-items: stretch;
  justify-content: space-between;
  margin: 0 auto;
  overflow: auto;

  .diaper-showcase {
    flex-basis: 45%;

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

      &.uppercase {
        text-transform: uppercase;
      }
    }

    ul {
      list-style-type: circle;
      margin: 0 0 1rem 1rem;

      li {
        font-size: 1rem;
        text-align: start;
      }

      li:nth-child(2) {
        color: $secondary-color;
      }
    }
  }

  .diaper-img {
    flex-basis: 55%;

    img {
      width: 100%;
      max-width: 584px;
      height: auto;
    }
  }
}

@media (max-width: 768px) {
  .content {
    flex-wrap: wrap;
    justify-content: center;
    padding: 0 15px;

    .diaper-showcase {
      flex-basis: 100%;

      h2 {
        font-size: 1.5rem;
      }

      p {
        font-size: 0.9rem;
      }

      ul {
        li {
          font-size: 0.9rem;
        }
      }
    }

    .diaper-img {
      flex-basis: 100%;
      margin-bottom: 2rem;
    }
  }
}

@media (max-width: 350px) {
  .content {
    .diaper-showcase {
      h2 {
        font-size: 1.2em;
      }
      p {
        font-size: 0.6rem;
      }
      ul {
        li {
          font-size: 0.6rem;
        }
      }
    }
  }
}
</style>