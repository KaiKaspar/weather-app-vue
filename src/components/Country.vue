<template>
    <div>
        <div class="m-5 w-75">
            <b-button v-b-toggle.collapse-1 class="w-100">United Kingdom</b-button>
            <b-collapse visible id="collapse-1" class="w-100">
                <b-card><ul>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="London" checked>London<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Bristol" >Bristol<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Manchester" >Manchester<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Edinburgh" >Edinburgh<br>
                </ul></b-card>
            </b-collapse>
        </div>
        <div class="m-5 w-75">
            <b-button v-b-toggle.collapse-2 class="w-100">USA</b-button>
            <b-collapse visible id="collapse-2" class="w-100">
                <b-card><ul>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Washington" >Washington<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="New York" >New York<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Los Angeles" >Los Angeles<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Miami" >Miami<br>
                </ul></b-card>
            </b-collapse>
        </div>
        <div class="m-5 w-75">
            <b-button v-b-toggle.collapse-3 class="w-100">Switzerland</b-button>
            <b-collapse visible id="collapse-3" class="w-100">
                <b-card><ul>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Zermatt" >Zermatt<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Zürich" >Zürich<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Geneva" >Geneva<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Bern" >Bern<br>
                </ul></b-card>
            </b-collapse>
        </div>
        <div class="m-5 w-75">
            <b-button v-b-toggle.collapse-4 class="w-100">Australia</b-button>
            <b-collapse visible id="collapse-4" class="w-100">
                <b-card><ul>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Sydney" >Sydney<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Melbourne" >Melbourne<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Brisbane" >Brisbane<br>
                <input v-model="location" v-on:change="selected" type="radio" name="city" value="Perth" >Perth<br>
                </ul></b-card>
            </b-collapse>
        </div>
   </div> 
</template>
    
<script>

export default {
    name: 'Country',
    props: {
        location: String,
        clicked: Function
    },
    methods: {
        selected: function() {
        this.clicked(this.location)
        }
    }
}
</script>

<style>
    input {
        float: left;
        margin-top: 1rem
    }
</style>