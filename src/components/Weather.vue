<template>
  <div class="weather">
    Wie ist das Wetter heute?

  <div>
    <input type="text" placeholder="Ort" v-model="ort" />
    <button @click="getWeather()">Zeig mir das Wetter</button>
  </div>

  <div v-if="!currentWeather.main">
    Bitte einen Ort eingeben und klicken...
  </div>

  <div v-if="currentWeather.main">
    Das Wetter:
    <p>Temperatur: {{currentWeather.main.temp | formatCelsius}}</p>
  </div>

  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: "Weather",
  props: {},
  data: function() {
    return {
      ort: '',
      currentWeather: {test: 1}
    };
  },
  methods: {
    async getWeather() {
      let response = await axios.get('https://api.openweathermap.org/data/2.5/weather?q=' + this.ort + '&appid=de09a5365dc2273611e32a1e28600cd9');

      this.currentWeather = response.data;
    }
  },
  computed: {
     temperatureC: function() {
       if (this.currentWeather.main)
       {
        return (this.currentWeather.main.temp - 32) * 5/9;
       } else {
         return 'unbekannt';
       }
     }
  },
  filters: {
    formatCelsius: function(value) {
      return (value-32)*5/9;
    }
  },
  created: function() {

  },
  mounted: function() {

  }
};
</script>

<style scoped lang="scss">

  .weather {
    border: solid 2px green;
  }

</style>
