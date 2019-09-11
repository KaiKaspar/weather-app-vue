<template>
    <div id="app">
        <div class="row">
            <Header/>
            <div class="column">
                <SelectCity :clicked="clicked" :location="location" :search="search"/>
            </div>
            <div class="column">
                <Weather :weather="weather" :location="location"/>
            </div>
        </div>
    </div>
</template>

<script>
import Header from './Header.vue'
import SelectCity from './SelectCity.vue'
import Weather from './Weather.vue'
import axios from 'axios';

export default {
    name: 'Dashboard',
    components: {
    Header,
    SelectCity,
    Weather
    }, 
    data () {
        return {
        location: "London",
        weather: {},
        search: ""
        }
    },
    mounted () {
        axios
        .get(`http://api.openweathermap.org/data/2.5/forecast?q=${this.location}&${key}`)
        .then(response => (this.weather = response.data))
    },
    methods: {
        clicked: function(value) {
        this.location = value
        axios
        .get(`http://api.openweathermap.org/data/2.5/forecast?q=${this.location}&${key}`)
        .then(response => (this.weather = response.data))
    }
    }
}
</script>

<style>
    .column {
    float: left;
    width: 50%;
    }
    .row:after {
    margin-top: 0px;
    content: "";
    display: table;
    clear: both;
    }
    @font-face {
    font-family: Gotham Light;
    src: url('../assets/Fonts/gotham light/Gotham-Light.otf') format("opentype");
    }
    @font-face {
    font-family: 'Gotham Black';
    src: url('../assets/Fonts/gotham black/GOTHAM-BLACK.TTF') format("truetype");
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


