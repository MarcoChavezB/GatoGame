<template>
    <div class="app" v-show="ocultarMenu" :class="{'animacionSalida':animacionSalida}">
        
        <div class="XO">
            <svg width="64" height="64" xmlns="http://www.w3.org/2000/svg"><path d="M15.002 1.147 32 18.145 48.998 1.147a3 3 0 0 1 4.243 0l9.612 9.612a3 3 0 0 1 0 4.243L45.855 32l16.998 16.998a3 3 0 0 1 0 4.243l-9.612 9.612a3 3 0 0 1-4.243 0L32 45.855 15.002 62.853a3 3 0 0 1-4.243 0L1.147 53.24a3 3 0 0 1 0-4.243L18.145 32 1.147 15.002a3 3 0 0 1 0-4.243l9.612-9.612a3 3 0 0 1 4.243 0Z" fill="#31C3BD" fill-rule="evenodd"/></svg>
            <svg width="64" height="64" xmlns="http://www.w3.org/2000/svg"><path d="M32 0c17.673 0 32 14.327 32 32 0 17.673-14.327 32-32 32C14.327 64 0 49.673 0 32 0 14.327 14.327 0 32 0Zm0 18.963c-7.2 0-13.037 5.837-13.037 13.037 0 7.2 5.837 13.037 13.037 13.037 7.2 0 13.037-5.837 13.037-13.037 0-7.2-5.837-13.037-13.037-13.037Z" fill="#F2B137"/></svg>
        </div>
        <div class="inps">
            <div class="title">
                <h1>Nombre de jugadores</h1>
            </div>
            <div class="inputs">
                <input type="text" v-model="nombreX" name="jugadorX" id="1" placeholder="X">
                <input type="text" v-model="nombreO" name="jugadorO" id="2" placeholder="O">
            </div>
            <div class="inf">
                <p>Se reflegara el nombre de cada jugador</p>
            </div>
        </div>
        
        <div class="btns">
            <button @click="ocultar(false); emisor(); mandarNombres()">Continuar</button>
        </div>
    </div>
</template>

<script setup>
import {ref} from 'vue'
import {defineEmits} from 'vue'

const ocultarMenu = ref(true)
var animacionSalida = ref(false)

const animacion = () => {
    animacionSalida.value = true
}

const ocultar = () =>{

    if (ocultarMenu.value === true) {
        animacion()
        setTimeout(() => {
            ocultarMenu.value = false    
        }, 350);
        
    }
}

// manera correcta de definir emits de hijo a padre
const emit = defineEmits(['botonClic'])

var nombreX = ref('');
var nombreO = ref('');

const mandarNombres = () => {
  emit('botonClic', nombreX.value, nombreO.value);
  console.log('se mandaron los nombres', nombreX.value, nombreO.value);
};

const emisor = () => {
  emit('botonClic');
}



</script>

<style scoped>


.app{
    animation:scale-up-center 1.0s; 
} 
@keyframes scale-up-center{ 

    0%{transform:scale(0)} 
    100%{transform:scale(1)} 
}

.animacionSalida{
    animation:scale-down-center 0.4s;
} 
@keyframes scale-down-center{
    0%{transform:scale(1)}
    100%{transform:scale(0.1)}
}



.app{
    display: flex;
  flex-direction: column;
  align-items: center;
}

.title h1 {
    color: #a8bfc9;
}

.inps{
    display: flex;
    flex-direction: column;
    justify-content: center;
    
}

.inps{
    background-color: #1f3641;
    align-items: center;
    border-radius: 15px;
    box-shadow: inset 0 -8px 0 #10212a;
    height: 260px;
    margin: .5em .5rem .5rem;
    width: 39.5em;
    outline: none;
    border: none;
}
.inputs{
    padding: 10px;
    border-radius: 10px;
    background: #10212a;

}

.inputs input:last-child{
    background-color: #f2b137;
    text-transform: uppercase;

}
.inputs input:first-child{
    background-color: #31c3bd;
    text-transform: uppercase;

}

input {
    width: 14em;
    height: 40px;
    border-radius: 5px;
    background-color: #a8bfc9;
    margin-right: .5rem;
    color: #1f3641;
    font-family: 'Rowdies', cursive;
    text-align: center;
}

.inf p{
    color: white;
}

.btns{
    display: flex;
    flex-direction: column;
}

.btns button{
    background-color: #65e9e4;
    box-shadow: inset 0 -4px 0 #118c87;
    width: 39.5em;
    height: 3.5em;
    cursor: pointer;
    border-radius: 8px;
    color: #1f3641;
    font-family: 'Rowdies', cursive;
}
</style>