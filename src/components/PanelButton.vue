<template>
  <div class="container">
    <div class="row gx-3">
      <div class="col-md-4 d-flex">
        <GameButton @click="cambio(1)" :texto="char[0]" :posicion="1"/>
      </div>
      <div class="col-md-4 d-flex">
        <GameButton @click="cambio(2)" :texto="char[1]" :posicion="2"/>
      </div>
      <div class="col-md-4 d-flex">
        <GameButton @click="cambio(3)" :texto="char[2]" :posicion="3"/>
      </div>
    </div>

    <div class="row gx-3">
      <div class="col-md-4 d-flex">
        <GameButton @click="cambio(4)" :texto="char[3]" :posicion= "4"/>
      </div>
      <div class="col-md-4 d-flex">
        <GameButton @click="cambio(5)" :texto="char[4]" :posicion="5"/>
      </div>
      <div class="col-md-4 d-flex">
        <GameButton @click="cambio(6)" :texto="char[5]" :posicion="6"/>
      </div>
    </div>

    <div class="row gx-3">
      <div class="col-md-4 d-flex">
        <GameButton @click="cambio(7)" :texto="char[6]" :posicion="7"/>
      </div>
      <div class="col-md-4 d-flex">
        <GameButton @click="cambio(8)" :texto="char[7]" :posicion="8"/>
      </div>
      <div class="col-md-4 d-flex">
        <GameButton @click="cambio(9)" :texto="char[8]" :posicion="9"/>
      </div>
    </div>
  </div>
</template>



<script setup>

import GameButton from './GameButtons.vue'
import { ref } from 'vue'

const char = ref(['', '', '', '', '', '', '', '', ''])
let turno = true

const cambio = (posicion) => {
  if (turno === true) {
    if (char.value[posicion - 1] === 'X' || char.value[posicion - 1] === '') {
      char.value[posicion - 1] = 'X'
      turno = false
      console.log('1')
    }
  } else if (turno === false) {
    if (char.value[posicion - 1] === 'O' || char.value[posicion - 1] === '') {
      char.value[posicion - 1] = 'O'
      turno = true
      console.log('2')
    }
  }

  const verificar = ganador()
  if(verificar){
    console.log('hay un ganador ')
  }
}

const ganador = () =>{
  const combinaciones = [
    [0, 1, 2], [3, 4, 5], [6, 7, 8], 
    [0, 3, 6], [1, 4, 7], [2, 5, 8], 
    [0, 4, 8], [2, 4, 6] 
  ]

  for (const combinacion of combinaciones){
    const [p1,p2,p3] = combinacion
    if (char.value[p1] !== '' && char.value[p1] === char.value[p2] && char.value[p2] === char.value[p3]){
      return char.value[p1]
    } 
  }

  return null

}

</script>

<style scoped>
.container {
  width: 40em;
  height: 34em;
}
</style>