<template>
    <div class="btn">
        <button @click="animacionEvent(); emisor()" :class="{ active:animacion }">{{ texto }}</button>
    </div>
</template>

<script setup>
import {defineProps, ref, defineEmits} from 'vue'
const animacion = ref (false)
defineProps({
    texto:{
        type:String,
        default: '',
    },

    posicion:{
        type:Number,
        default: 0
    },

})

const animacionEvent = (posicion) => {
  console.log('btn clic', posicion)
  animacion.value = true;

  setTimeout(() =>{
    animacion.value = false;
  }, 1000);
}

const emit = defineEmits(['turno']);

const emisor = () => {
  emit('turno');
  console.log('emitiendo señal')
}



</script>


<style scoped>
button {
  background-color: #1f3641;    
  align-items: center;
  border-radius: 15px;
  box-shadow: inset 0 -8px 0 #10212a;
  display: flex;
  height: 180px;
  justify-content: center;
  width: 180px;
  outline: none;
  border: none;
  font-family: 'Cherry Bomb One', cursive;
  color: white;
  position: relative;
  opacity: 0,5;
  font-size: 5em;
}

.active {
    animation:animacion 0.4s ease-in-out both; 
    color: #31c3bd;
} 
    
    @keyframes animacion{
    0%{
    box-shadow:0 0 0 0 transparent; 
    }
    100%{
    box-shadow:0 0 20px 0 rgb(49, 195, 189);
    }
}



</style>
