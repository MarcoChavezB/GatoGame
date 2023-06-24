  <template>
    <div class="et">
        <div class="title">
            <h4>Ganaste! Wazzzaaa 👻</h4>
        </div>
        <div class="desc">
            <svg width="64" height="64" xmlns="http://www.w3.org/2000/svg"><path d="M15.002 1.147 32 18.145 48.998 1.147a3 3 0 0 1 4.243 0l9.612 9.612a3 3 0 0 1 0 4.243L45.855 32l16.998 16.998a3 3 0 0 1 0 4.243l-9.612 9.612a3 3 0 0 1-4.243 0L32 45.855 15.002 62.853a3 3 0 0 1-4.243 0L1.147 53.24a3 3 0 0 1 0-4.243L18.145 32 1.147 15.002a3 3 0 0 1 0-4.243l9.612-9.612a3 3 0 0 1 4.243 0Z" fill="#31C3BD" fill-rule="evenodd"/></svg>            <h1>Tomo la partida</h1>
        </div>
        <div class="btns">
            <button class="quitar">Quitar</button>
            <button class="siguiente">Siguiente ronda</button>
        </div>
    </div>
  </template>

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
    color: #31c3bd;
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