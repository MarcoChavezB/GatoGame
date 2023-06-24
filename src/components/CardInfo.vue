<template>
    <div class="barra">
        <div class="imgs">
            <!--Variables para cambiar respecto al tuno-->
            <svg width="64" height="64" xmlns="http://www.w3.org/2000/svg"><path d="M15.002 1.147 32 18.145 48.998 1.147a3 3 0 0 1 4.243 0l9.612 9.612a3 3 0 0 1 0 4.243L45.855 32l16.998 16.998a3 3 0 0 1 0 4.243l-9.612 9.612a3 3 0 0 1-4.243 0L32 45.855 15.002 62.853a3 3 0 0 1-4.243 0L1.147 53.24a3 3 0 0 1 0-4.243L18.145 32 1.147 15.002a3 3 0 0 1 0-4.243l9.612-9.612a3 3 0 0 1 4.243 0Z" fill="#31C3BD" fill-rule="evenodd"/></svg>
            <svg width="64" height="64" xmlns="http://www.w3.org/2000/svg"><path d="M32 0c17.673 0 32 14.327 32 32 0 17.673-14.327 32-32 32C14.327 64 0 49.673 0 32 0 14.327 14.327 0 32 0Zm0 18.963c-7.2 0-13.037 5.837-13.037 13.037 0 7.2 5.837 13.037 13.037 13.037 7.2 0 13.037-5.837 13.037-13.037 0-7.2-5.837-13.037-13.037-13.037Z" fill="#F2B137"/></svg>
        </div>
        <div class="turno">
            <!--Cambiar X por el turno que es-->
            <h1> X </h1><p>Turno</p>
        </div>
        <div class="btn-restart">
            <button></button>
        </div>
    </div>
</template>


<style scoped>
.imgs{
    margin-left: 20px;
    margin-left: -40px;
}

.turno{
    align-items: center;
    background-color: #1f3641;
    border-radius: 10px;
    box-shadow: inset 0 -4px 0 #10212a;
    display: flex;
    height: 52px;
    width: 150px;
    font-family: Outfit,sans-serif;
    color: white;
    justify-content: space-evenly;
    
}

.barra{
    align-items: center;
    display: flex;
    justify-content: space-between;
    width: 445px;
}

.btn-restart button{
    background-color: #a8bfc9;
    border: 0;
    border-radius: 10px;
    box-shadow: inset 0 -4px 0 #6b8997;
    height: 52px;
    width: 52px;
    background-image: url('/src/assets/icreset.png');
    text-align: center;
    
}

.turno h1{
    font-family: 'Rowdies', cursive;
    color: #a8bfc9;
}
.turno p{
    font-family: Outfit,sans-serif;
    font-size: 1.8em;
    margin-bottom: 17px;
}

.btn-restart #res {
    background-repeat: no-repeat;
    background-size: 20px;
    background: #a8bfc9;
}

</style>

