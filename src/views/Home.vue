<template>
  <Trial v-bind:diapers="diapers" />
</template>

<script>
import Trial from "../components/Trial";

export default {
  name: "Home",
  components: {
    Trial
  },
  data() {
    return {
      diapers: [
        {
          id: 1,
          name: "1",
          weight: "(2-5 KG)",
          img: "diaper1.jpg"
        },
        {
          id: 2,
          name: "2nd",
          weight: "(4-8 KG)",
          img: "diaper2.jpg"
        },
        {
          id: 3,
          name: "3rd",
          weight: "(6-10 KG)",
          img: "diaper3.jpg"
        },
        {
          id: 4,
          name: "4th",
          weight: "(9-14 KG)",
          img: "diaper4.jpg"
        },
        {
          id: 5,
          name: "5",
          weight: "(11-16 KG)",
          img: "diaper5.jpg"
        }
      ]
    };
  }
};
</script>