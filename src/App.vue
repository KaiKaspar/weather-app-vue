<template>
  <div id="app">
    <Dashboard :function="clicked" :location="location" :weather="weather"/>
  </div>
</template>

<script>
import Dashboard from './components/Dashboard.vue'
import axios from 'axios';

export default {
  name: 'app',
  components: {
    Dashboard
  },
  data () {
    return {
      location: "London",
      weather: {}
    }
  },
  mounted () {
    axios
      .get(`http://api.openweathermap.org/data/2.5/forecast?q=${this.location}&appid=${key}`)
      .then(response => (this.weather = response.data))
  },
  methods: {
    clicked: function() {
    axios
      .get(`http://api.openweathermap.org/data/2.5/forecast?q=${this.location}&appid=${key}`)
      .then(response => (this.weather = response.data))
        }
    }
}
</script>

<style>
  @font-face {
  font-family: Gotham Light;
  src: url('./assets/Fonts/gotham light/Gotham-Light.otf') format("opentype");
  }
  @font-face {
  font-family: 'Gotham Black';
  src: url('./assets/Fonts/gotham black/GOTHAM-BLACK.TTF') format("truetype");
  }
  #app {
    font-family: 'Gotham Light', 'Gotham Black';
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 0px;
  }
</style>
