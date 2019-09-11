<template>
    <div.weather>
        <Day :location="location" :weather="weather"/>
    </div.weather>
</template>

<script>
import Day from './Day.vue'
export default {
    name: 'Weather',
    components: {
    Day
  },
  props: {
    weather: Object,
    location: String
  }
}
</script>

<style>
    div weather {
        float: right;
    }
</style>
