<template>
    <div class="et" v-show="mostrar">
        <div class="title">
            <h4>Nadie gano... 😞</h4>
        </div>
        <div class="desc">
            <h1>No pusieron pared 👻</h1>
            <br>
        </div>
        <div class="btns">
            <button class="quitar" @click="recargar">Quitar</button>
            <button class="siguiente" @click="jugar">Siguiente ronda</button>
        </div>
    </div>
  </template>

<script setup>
import {ref} from 'vue'

var mostrar = ref(true)

const jugar = () =>{
    if (mostrar.value === true){
        mostrar.value = false
        console.log("funcionando")
    }
}

const recargar = () =>{
    location.reload();
}

</script>

<style scoped>
.et{
    align-items: center;
    background-color: #1f3641;
    display: flex;
    flex-direction: column;
    height: 266px;
    margin-top: 20rem;
    width: 100%;
}

.title{
    color: #a8bfc9;
    font-size: 16px;
    font-weight: 700;
    margin-top: 3rem;
    text-align: center;
}

.desc{
    align-items: center;
    display: flex;
    justify-content: center;
}

.desc, h1{
    font-family: Outfit,sans-serif;
    font-size: 40px;
    font-weight: 700;
    margin-left: 1rem;
    color: #31c3bd;
}

.btns{
    display: block;
}

.quitar, .siguiente{
    border: 0;
    border-radius: 10px;
    color: #1a2a33;
    font-family: Outfit,sans-serif;
    font-weight: 700;
    height: 52px;
}
.quitar{
    background-color: #a8bfc9;
    box-shadow: inset 0 -4px 0 #6b8997;
    margin-right: .5rem;
    width: 76px;
    cursor: pointer;
}

.siguiente{
    background-color: #f2b137;
    box-shadow: inset 0 -4px 0 #cc8b13;
    margin-left: .5rem;
    width: 146px;
    cursor: pointer;
}


</style>