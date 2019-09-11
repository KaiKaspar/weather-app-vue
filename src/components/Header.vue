<template>
    <div class="ah">
        <h4><a>WEATHER</a><span><b>APP</b></span></h4>
    </div>
</template>

<script>


export default {
    name: 'Header',
    props: {
        msg: String
    }
}
</script>

<style>
    .ah {
    top: 0;
    left: 0;
    width: 100%;
    background-color: black;
    height: 3rem;
    }
    h4 {
    float: left;
    font-size: 1rem;
    display: block;
    text-align: center;
    padding-left: 5rem;
    padding-top: 0.8rem;
    color: white;
    }
    h4 a {
    font-family: Gotham Light;
    color: grey;
    }
    h4 b {
    font-family: 'Gotham Black';
    }
</style>


