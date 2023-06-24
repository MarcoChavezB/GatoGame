<template>
  <div class="app">
    <div class="content">
      <div class="content" :class="{'opacidad':aplicarOpacidad}">
        <!--Encabezado o etiqueta de informacion-->
        
      </div>
      <div class="panel" :class="{'panel-juego':aplicarOpacidad}">
        <!--Panel de juego-->
        <PanelButton :nombreX ="nombreX" :nombreO="nombreO"/>
      </div>
      <div class="history" :class="{'opacidad':aplicarOpacidad}">
        <!--etiqueta historial-->
      </div>
    </div>
    <div class="msg" :class="{'opacidad':aplicarOpacidad}">
      <!--Mensajes de perdedor o ganador-->
    </div>
    <!--Menu para iniciar el juego-->
    <div class="menu-inicial">
      <GameMenu @botonClic="() => ocultar()"/>
    </div>
  </div>
</template>

<script setup>
//import WinnerMessage from './components/WinnerMessage'
//import LooseMessage from './components/LooseMessage'
import PanelButton from './components/PanelButton'
import GameMenu from './components/GameMenu'
import {ref} from 'vue';




var aplicarOpacidad = ref(true);
var panelOpacidad = ref(false);
var nombreX = ref('')
var nombreO = ref('')

// funcion de escucha para el componente hijo al padre
const ocultar = () => {
  //logica de cuando se clikeo el boton del hijo
  aplicarOpacidad.value = false;
  panelOpacidad.value = true;
  console.log('opacidad funcionando')
}

</script>

<style scoped>

/*Estilo de tipo booleano*/ 
.opacidad{
  opacity: 0.3;
}

.panel-juego{
  position: relative;
  opacity: 0.3;
  z-index: -1;
}


.menu-inicial{
  margin-top: -48em;
  margin-right: -2.5em;
}

.content{
  display: flex;
  flex-direction: column;
  align-items: center;
}

.app{
  margin-top: 100px;
}
</style>