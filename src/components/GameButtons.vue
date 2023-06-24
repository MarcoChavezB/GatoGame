<template>
    <div class="btn">
        <button @click="cambio" :class="{ active:animacion }">{{ texto }}</button>
    </div>
</template>

<script setup>
import {defineProps, ref} from 'vue'

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

const animacion = ref (false)

const cambio = (posicion) => {
  console.log('btn clic', posicion)
  animacion.value = true;

  setTimeout(() =>{
    animacion.value = false;
  }, 1000);
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
  margin: .5em .5rem .5rem;
  width: 180px;
  outline: none;
  border: none;
  font-family: 'Cherry Bomb One', cursive;
  color: white;
  position: relative;
  opacity: 0,5;
}


.active {
    animation:animacion 0.4s ease-in-out both 
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
