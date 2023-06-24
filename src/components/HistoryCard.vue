<template>
    <div class="his">
        <div class="playerX">
            <div class="content">
                <p>Marco</p>
                <h4>0</h4>
            </div>
        </div>
        <div class="partidas">
            <div class="content">
                <p>N partidas</p>
                <h4>0</h4>
            </div>
        </div>
        <div class="playerO">
            <div class="content">
                <p>Jugador</p>
                <h4>0</h4>
            </div>
        </div>
    </div>
</template>

<style setuo>
.his{
    display: flex;
}
.playerX {
    background-color: #31c3bd;
    border-radius: 15px;
    height: 72px;
    width: 190px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 1.5em;
}

.partidas {
    background-color: #a8dfc9;
    border-radius: 15px;
    height: 72px;
    width: 190px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 1.5em;
}

.playerO {
    background-color: #f2b137;
    border-radius: 15px;
    height: 72px;
    width: 190px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.content {
    text-align: center;
}

p{
    font-size: 15px;
    font-weight: medium;
    margin: .8rem 0 0; 
    font-family: Outfit,sans-serif;
}

h4 {
    font-size: 24px;
    font-weight: 700;
    margin: 10px;
    font-family: 'Roboto', sans-serif;
}
</style>