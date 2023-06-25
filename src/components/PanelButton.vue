<template>
  <div class="ctGeneral">
    <div class="nombres">
      <GameMenu @botonClic="recibirNombres" />
    </div>
    <div class="ganador">
      <WinnerMessage v-if="mostrarGanador" @seguirJugando="seguir" />
      <LooseMessage v-if="mostrarPerdedor" @seguirJugando="seguir" />
    </div>
    <div class="container" :class="{ 'opacidadGanadora': opacidad }">
      <div class="row gx-3">
        <div class="encabezado" :class="{ 'opacidadGanadora': opacidad }">
          <CardInfo @limpiarbtns="limpiar" :title="turnoJugador" />
        </div>
        <div class="col-md-4 d-flex" :class="{ 'opacidadGanadora': opacidad }">
          <GameButton @click="cambio(1)" :texto="char[0]" :posicion="1" />
        </div>
        <div class="col-md-4 d-flex" :class="{ 'opacidadGanadora': opacidad }">
          <GameButton @click="cambio(2)" :texto="char[1]" :posicion="2" />
        </div>
        <div class="col-md-4 d-flex" :class="{ 'opacidadGanadora': opacidad }">
          <GameButton @click="cambio(3)" :texto="char[2]" :posicion="3" />
        </div>
      </div>

      <div class="row gx-3" :class="{ 'opacidadGanadora': opacidad }">
        <div class="col-md-4 d-flex">
          <GameButton @click="cambio(4)" :texto="char[3]" :posicion="4" />
        </div>
        <div class="col-md-4 d-flex">
          <GameButton @click="cambio(5)" :texto="char[4]" :posicion="5" />
        </div>
        <div class="col-md-4 d-flex">
          <GameButton @click="cambio(6)" :texto="char[5]" :posicion="6" />
        </div>
      </div>
      <div class="row gx-3" :class="{ 'opacidadGanadora': opacidad }">
        <div class="col-md-4 d-flex">
          <GameButton @click="cambio(7)" :texto="char[6]" :posicion="7" />
        </div>
        <div class="col-md-4 d-flex">
          <GameButton @click="cambio(8)" :texto="char[7]" :posicion="8" />
        </div>
        <div class="col-md-4 d-flex">
          <GameButton @click="cambio(9)" :texto="char[8]" :posicion="9" />
        </div>
      </div>
    </div>
    <div class="history" :class="{ 'opacidadGanadora': opacidad }">
      <HistoryCard :marcadorA="puntosA" :marcadorB="marcadorB" :marcadorC="puntosB" :nombreX="nombreA"
        :nombreO="nombreB" />
    </div>
  </div>
</template>



<script setup>
import GameMenu from './GameMenu.vue'
import GameButton from './GameButtons.vue'
import WinnerMessage from './WinnerMessage.vue'
import CardInfo from './CardInfo.vue'
import HistoryCard from './HistoryCard'
import LooseMessage from './LooseMessage'
import { ref } from 'vue'



const char = ref(['', '', '', '', '', '', '', '', ''])
var turnoJugador = ref('X')
var marcadorB = ref(0)
var puntosA = ref(0)
var puntosB = ref(0)
var nombreA = ref('NaN')
var nombreB = ref('NaN')
var opacidad = ref(true)
var mostrarGanador = ref(false)
var mostrarPerdedor = ref(false)
let turno = true


const recibirNombres = (x, o) => {
  if (x === '' || o === '') {
    alert('Porfabor ingrese los nombres')
    location.reload()
  }else {
    nombreA.value = x
    nombreB.value = o
    console.log('nombres recibidos', nombreA.value, nombreB.value)
    opacidad.value = false
  }
}

const seguir = () => {
  mostrarGanador.value = false
  console.log('mostrar ganador inicializada en false')
}


const cambio = (posicion) => {
  if (turno === true) {
    if (char.value[posicion - 1] === 'X' || char.value[posicion - 1] === '') {
      char.value[posicion - 1] = 'X'
      turno = false
      console.log('1')
      turnoJugador.value = 'O'
    }
  } else if (turno === false) {
    if (char.value[posicion - 1] === 'O' || char.value[posicion - 1] === '') {
      char.value[posicion - 1] = 'O'
      turno = true
      console.log('2')
      turnoJugador.value = 'X'
    }
  }

  const verificar = ganador()
  if (verificar) {
    if (verificar === 'X') {
      //if para saber si el ganador fue X o O
      mostrarGanador.value = true
      opacidad.value = true

      setTimeout(() => {
        opacidad.value = false
        mostrarGanador.value = false
        puntosA.value++;
        limpiar();
      }, 3000);

    } else if (verificar === 'O') {
      console.log('ganador O')
      mostrarPerdedor.value = true
      opacidad.value = true
      setTimeout(() => {
        opacidad.value = false
        mostrarPerdedor.value = false
        puntosB.value++;
        limpiar();
      }, 3000);
    }
  }
}

const ganador = () => {
  const combinaciones = [
    [0, 1, 2], [3, 4, 5], [6, 7, 8],
    [0, 3, 6], [1, 4, 7], [2, 5, 8],
    [0, 4, 8], [2, 4, 6]
  ]

  for (const combinacion of combinaciones) {
    const [p1, p2, p3] = combinacion
    if (char.value[p1] !== '' && char.value[p1] === char.value[p2] && char.value[p2] === char.value[p3]) {
      return char.value[p1]
    } 
  }
  return null
}

const limpiar = () => {
  console.log('señal de reset')
  char.value = ['', '', '', '', '', '', '', '', '']
  marcadorB.value++
}


</script>

<style scoped>
.opacidadGanadora {
  position: relative;
  opacity: 0.5;
  z-index: -1;
}

.nombres {
  position: absolute;
  z-index: 2;
  margin-top: 10em;
  margin-left: 0.8em;
}


.container {
  width: 40em;
  height: 34em;
}

.history {
  margin-left: 25px;
  margin-top: 120px;

}

.ganador {
  position: absolute;
  right: 0%;
  width: 100%;
  margin-top: -5em;
}

.encabezado {
  margin-left: 70px;
}
</style>