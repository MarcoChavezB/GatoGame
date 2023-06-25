<template>
  <div class="app">
    <div class="content">
      <div class="panel" :class="{'panel-juego':aplicarOpacidad}">
        <PanelButton :nombreX ="nombreX" :nombreO="nombreO"/>
      </div>
    </div>
    <div class="menu-inicial">
    </div>
  </div>
</template>

<script setup>
import PanelButton from './components/PanelButton'
import {ref} from 'vue';

var aplicarOpacidad = ref(false);
var nombreX = ref('')
var nombreO = ref('')

</script>

<style scoped>


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