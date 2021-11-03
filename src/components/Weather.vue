<template>
  <div class="container">
    <h1 class="my-4">Application Météo avec Vue.js</h1>

    <div class="form-group mb-5">
      <label for="position"> Entrez le nom d'une ville : </label>
      <input
        type="text"
        id="position"
        class="form-control"
        v-model="requeste"
        v-on:keypress.enter="startWeather"
      />
    </div>

    <div class="w-75 m-auto" v-if="weath">
      <h3 class="text-center mb-3">Position : {{ weath.name }}</h3>
      <div class="card text-center p-5">
        <p class="text-display">
          Température : {{ weath.main.temp.toFixed() }} °C
        </p>
        <p class="text-display">Temps : {{ weath.weather[0].description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Weather",
  data() {
    return {
      requeste: "",
      weath: undefined,
      api_code: `931ff49c2f4a687fff6ba226727a867f`,
      url_search: "https://api.openweathermap.org/data/2.5/weather?",
    };
  },
  methods: {
    startWeather() {
      axios
        .get(
          `${this.url_search}q=${this.requeste}&units=metric&APPID=${this.api_code}&lang=fr`
        )
        .then((response) => {
          this.weath = response.data;
        });
      this.requeste = "";
    },
  },
};
</script>

<style>
.text-display {
  font-size: 30px;
  font-weight: 300;
  line-height: 1.2;
}
</style>