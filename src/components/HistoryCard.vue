<template>
    <div class="his">
        <div class="playerX">
            <div class="content">
                <p>{{ nombreX }}</p>
                <h4>{{ marcadorA }}</h4>
            </div>
        </div>
        <div class="partidas">
            <div class="content">
                <p>N partidas</p>
                <h4>{{ marcadorB }}</h4>
            </div>
        </div>
        <div class="playerO">
            <div class="content">
                <p>{{ nombreO }}</p>
                <h4>{{ marcadorC }}</h4>
            </div>
        </div>
    </div>
</template>

<script setup>
import {defineProps} from 'vue'

defineProps({
    marcadorA:{
        type: Number,
        default: 0
    },
    marcadorB:{
        type: Number,
        default: 0
    },
    marcadorC:{
        type: Number,
        default: 0
    },
    nombreX:{
        type: String,
        default: "Default",
    },
    nombreO:{
        typeof: String,
        default: "Default",
    }
})
</script>

<style setuo>
.his{
    display: flex;
    text-transform: uppercase;
}
.playerX {
    background-color: #31c3bd;
    border-radius: 15px;
    height: 72px;
    width: 190px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 1.5em;
}

.partidas {
    background-color: #a8dfc9;
    border-radius: 15px;
    height: 72px;
    width: 190px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 1.5em;
}

.playerO {
    background-color: #f2b137;
    border-radius: 15px;
    height: 72px;
    width: 190px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.content {
    text-align: center;
}

p{
    font-size: 15px;
    font-weight: medium;
    margin: .8rem 0 0; 
    font-family: 'Rowdies', cursive;
}

h4 {
    font-size: 24px;
    font-weight: 700;
    margin: 10px;
    font-family: 'Roboto', sans-serif;
}
</style>