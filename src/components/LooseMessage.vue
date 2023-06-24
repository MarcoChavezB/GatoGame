<template>
    <div class="et">
        <div class="title">
            <h4>Acabas de perder xd 👻</h4>
        </div>
        <div class="desc">
            <svg width="64" height="64" xmlns="http://www.w3.org/2000/svg"><path d="M32 0c17.673 0 32 14.327 32 32 0 17.673-14.327 32-32 32C14.327 64 0 49.673 0 32 0 14.327 14.327 0 32 0Zm0 18.963c-7.2 0-13.037 5.837-13.037 13.037 0 7.2 5.837 13.037 13.037 13.037 7.2 0 13.037-5.837 13.037-13.037 0-7.2-5.837-13.037-13.037-13.037Z" fill="#F2B137"/></svg>            
            <h1>Tomo la partida</h1>
        </div>
        <div class="btns">
            <button class="quitar" @click="recargar" >Quitar</button>
            <button class="siguiente">Siguiente ronda</button>
        </div>
    </div>
  </template>

<script setup>

const recargar = () =>{
    location.reload()
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
    color: #f2b137;
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