<template>
  <div class="app">
    <div class="content">
      <div class="info">
        <!--Encabezado o etiqueta de informacion-->
        <CardInfo />
      </div>
      <div class="panel">
        <!--Panel de juego-->
        <PanelButton />
      </div>
      <div class="history">
        <!--etiqueta historial-->
        <HistoryCard />
      </div>
    </div>
    <div class="msg">
      <!--Mensajes de perdedor o ganador-->
    </div>
    <!--Menu para iniciar el juego-->
    <div class="menu-inicial">
      <GameMenu @escucharHijo="ocultarHijo"/>
    </div>
  </div>
</template>

<script setup>
import HistoryCard from './components/HistoryCard'
import WinnerMessage from './components/WinnerMessage'
import LooseMessage from './components/LooseMessage'
import PanelButton from './components/PanelButton'
import CardInfo from './components/CardInfo'
import GameMenu from './components/GameMenu'

let ocultar = false 

const ocultarHijo = (value) =>{
  this.ocultar = value
}

</script>

<style scoped>

.info, .panel, .history, .msg{
  opacity: 0.3;
}
.panel{
  z-index: -1;
}
.menu-inicial{
  margin-top: -48em;
  margin-right: -1.5em;
 
}
.history{
  margin-left: 30px;
  margin-top: 99px;
  
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