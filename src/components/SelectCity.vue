<template>
    <div>
        <div>
        <h2>Select City...</h2>
        <b-form-input v-model="search" v-on:keyup="entered" class="w-25" placeholder="Search" value=""></b-form-input>
        </div>
        <div>
        <Country :clicked="clicked" :location="location"/>
        </div>
    </div>
</template>

<script>
import Country from './Country.vue'

export default {
    name: 'SelectCity',
    props: {
        location: String,
        search: String,
        clicked: Function,
        searched: Function
    },
    methods: {
        entered: function(e) {
        if (e.keyCode === 13) {
            this.clicked(this.search)
        }
        }
    },
    
    components: {
    Country
  }
}
</script>

<style>
    h2 {
    font-family: Gotham Light;
    color: gray;
    float: left;
    display: block;
    text-align: left;
    padding-left: 3rem;
    padding-right: 3rem;
    margin-top: 4rem;
    }
</style>


