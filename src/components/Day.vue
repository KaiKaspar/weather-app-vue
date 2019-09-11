<template>
    <div class="m-5 w-75">
        <b-card>
            <b-img v-if="this.weather.list[1].weather[0].main === 'Clouds'" v-bind="mainProps" right :src="require('../static/assets/Images/overcast.png')" alt="Right image"></b-img>
            <b-img v-if="this.weather.list[1].weather[0].main === 'Rain'" v-bind="mainProps" right :src="require('../static/assets/Images/light_rain.png')" alt="Right image"></b-img>
            <b-img v-if="this.weather.list[1].weather[0].main === 'Clear'" v-bind="mainProps" right :src="require('../static/assets/Images/cloudy2.png')" alt="Right image"></b-img>
            <b-img v-if="this.weather.list[1].weather[0].main === 'Sun'" v-bind="mainProps" right :src="require('../static/assets/Images/sunny.png')" alt="Right image"></b-img>
            <b-img v-if="this.weather.list[1].weather[0].main === 'Snow'" v-bind="mainProps" right :src="require('../static/assets/Images/snow4.png')" alt="Right image"></b-img>

            <b-card-text>
                <h2>{{this.location}}</h2><br><br>
                <weath>
                <h1>{{ Math.round(this.weather.list[1].main.temp - 273.15) }}°C</h1>
                <p class="text">{{ this.weather.list[1].weather[0].main }}</p>
                <div class="date">
                <p v-if="this.weatherDate === dateToday">Today</p>
                <p v-if="this.weatherDate !== dateToday">{{weatherDate}}</p>
                <p v-if="this.weatherTime < '12:00'">{{weatherTime}} am</p>
                <p v-if="this.weatherTime >= '12:00'">{{weatherTime}} pm</p>
                </div>
                </weath>
            </b-card-text>
        </b-card>
    </div>
</template>

<script>
let day = new Date().getDate()
    let month = new Date().getMonth() + 1
    let year = new Date().getFullYear()
    {month < 9 ? month = '0' + month: null}
    {day < 9 ? day = '0' + day: null}
    let date = year + '-0' + month + '-' + day

export default {
    name: 'Day',
  props: {
    weather: Object,
    location: String
  },
  data() {
      return {
        mainProps: { width: 100, height: 100 },
        dateToday: date,
        weatherDate: this.weather.list[1].dt_txt.slice(0, 10),
        weatherTime: this.weather.list[1].dt_txt.slice(10, 16)
      }
    }
}
</script>

<style>
    h1 {
        font-family: 'Gotham Black';
        display: inline;
        padding-right: 1rem
    }
    .text {
        font-family: 'Gotham Black';
        display: inline
    }
    .date {
        margin-left: 2.5rem;
        text-align: left;
    }
    weath {
        margin-left: -10rem;
    }
</style>
