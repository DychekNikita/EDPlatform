<template>
  <div class="info-block col xl9 l9 m9 s9 z-depth-1">
    <h3 class="info-block-title black-text">Заголовок</h3>
    <div class="small">
      <line-chart :chart-data="datacollection"></line-chart>
      <button @click="fillData()">Randomize</button>
    </div>
  </div>
</template>
<script>
import LineChart from "./LineChart.js";

export default {
  components: {
    LineChart
  },
  data() {
    return {
      datacollection: null
    };
  },
  mounted() {
    this.fillData();
  },
  methods: {
    fillData() {
      this.datacollection = {
        labels: [this.getRandomInt(), this.getRandomInt()],
        datasets: [
          {
            label: "Data One",
            backgroundColor: "#f87979",
            data: [this.getRandomInt(), this.getRandomInt()]
          },
          {
            label: "Data One",
            backgroundColor: "#f87979",
            data: [this.getRandomInt(), this.getRandomInt()]
          }
        ]
      };
    },
    getRandomInt() {
      return Math.floor(Math.random() * (50 - 5 + 1)) + 5;
    }
  }
};
</script>
<style>
.info-block {
  margin: 0 !important;
  padding: 25px !important;
  margin: 0;
  border-radius: 10px;
  min-height: 500px !important;
  box-sizing: border-box;
}
.info-block-title {
  margin: 0;
  color: black;
  font-size: 28px;
  font-weight: bold;
}

.small {
  max-width: 600px;
  margin: 150px auto;
}
</style>
