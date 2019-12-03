<template>
  <div class="table-games">
    <div class="row">
      <div class="col-md-5">
        <h1> Conquistas</h1>
          <div
            v-for="(item, index) in conquistas"
            :key="index"
            class="gameProgress">
            <div class="bar">
            <div class="bar__percent"
              :style="{ width: `${percentWidthBar(item.progress)}` }">
            </div>
            <div class="bar__content">
              <div class="bar__content-txt-one">
                {{ item.name.toUpperCase() }}
              </div>

              <div class="bar__content-txt-percent">
                {{`${((item.progress * 100) / 100).toFixed(2)}%`}}
              </div>
              <div class="bar__content-txt-two">

              </div>
            </div>

            <div class="bar__image">
                <img :src="item.img" alt="">
            </div>
            </div>
        </div>
      </div>

      <div class="col-md-7">
        <h1>Missao em  Andamento</h1>
        <div class="missao-descricao">
          <p>Realize essa missão junto com o <strong>Player 2</strong>.</p>
          <p>Até a missão final dessa temporada, contiuem jogando no modo multiplayer e ambos ajudando um ao outro nas missões. Ao térmido da temporada o ideal é estarem com todas as conquistas desbloquedas.</p>
          <div class="row objtivos ">
            <div class="col-md-12">
              <h3 style="text-align: left">Objetivos</h3>
              <ul>
                <li v-for="obj in objetivos" :key="obj">
                  {{obj.descricao}}
                  <img v-if="obj.status == 'Concluido'" src="https://image.flaticon.com/icons/svg/190/190411.svg" width="20" height="20">
                  <img v-if="obj.status == 'Em Andamento'" src="https://image.flaticon.com/icons/svg/143/143355.svg" width="20" height="20">
                  <img v-if="obj.status == 'Falha'" src="https://image.flaticon.com/icons/svg/497/497738.svg" width="20" height="20">

                  <small v-if="obj.status == 'Concluido'" style="color: green"> | {{obj.status}}</small>
                  <small v-if="obj.status == 'Em Andamento'"> | {{obj.status}}</small>
                  <small v-if="obj.status == 'Falha'" style="color: red"> | {{obj.status}}</small>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:'GamePogress',
  data() {
    return {
      conquistas: {
        0:{
        "name": "Ficar Juntinhos",
        "progress": 100,
        "trofeus": 100,
        "img": "imgs/vida4.jpg"
        },
        1:{
        "name": "Saudades",
        "progress": 100,
        "trofeus": 100,
        "img": "imgs/vida10.jpg"
        },
        2:{
        "name": "Ver todos os dias",
        "progress": 20,
        "trofeus": 1000,
        "img": "imgs/vida26.jpg"
        },
        3:{
        "name": "Gostar de Basquete",
        "progress": 100,
        "trofeus": 1000,
        "img": "imgs/nba.jpg"
        },
        4:{
        "name": "Amizade",
        "progress": 100,
        "trofeus": 1000,
        "img": "imgs/vida5.jpg"
        },
        5:{
        "name": "Respeito",
        "progress": 100,
        "trofeus": 1000,
        "img": "imgs/vida5.jpg"
        },
        6:{
        "name": "Assistir filmes",
        "progress": 5,
        "trofeus": 1000,
        "img": "https://assets.b9.com.br/wp-content/uploads/2016/06/netflix-logo-thumb.jpg"
        },
        7:{
        "name": "Viagem juntos",
        "progress": 100,
        "trofeus": 1000,
        "img": "imgs/vida21.jpg"
        },
        10:{
        "name": "Tirar foto maluquinha",
        "progress": 100,
        "trofeus": 500,
        "img": "imgs/vida12.jpg"
        },
        11:{
        "name": "EASTEREGG (vejam um filme bizzaro no 1 econtro)",
        "progress": 100,
        "trofeus": 300,
        "img": "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTodRr-MpQXfQN1oiATQDGJLrCWly-13yIPbNNikCTf3JgA9ENL"
        },
        15:{
        "name": "O Grande Dia (Casamento)",
        "progress": 0,
        "trofeus": 10000,
        "img": "imgs/vida9.jpg"
        },
      },
      objetivos:{
        0: {
          "descricao": "Fale sempre com Deus sobre vocês",
          "status": "Concluido"
        },
        1: {
          "descricao": "Ensine todos os dias algo novo um para outro (Noobs)",
          "status": "Em Andamento"
        },
        2: {
          "descricao": "Não Seja TEIMOSA hehe",
          "status": "Falha"
        },
        3: {
          "descricao": "0 vidas? Acopanhe o(a) parceiro(a) em consultas médicas",
          "status": "Concluido"
        },
        4: {
          "descricao": "Melhor que ligação. Faça videos chamadas",
          "status": "Concluido"
        },
        5: {
          "descricao": "Leve a 10/10 num restaurante.",
          "status": "Concluido"
        }
      }
    }
  },
  methods: {
        // Da o valor de largura da barra de XP dos games
    percentWidthBar(value){
      return `${(value*100)/100}%`
    }
  },
}
</script>


<style scoped>
/* Tabelas Games */
.table-games{
  padding-bottom: 9px;
  background: #efeaea
}
.gameanalytics{
  overflow-y: scroll;
  min-width: 300px;
  height: 248px;
  border: 1px solid #0076d770;
  background: #27384a;
}
.gameProgress{
  margin-bottom: 16px;
  position:relative;
  border: 1px solid #fd1c56;
  position:relative;
  padding:3px;
}
.gameProgress img{
  width:auto;
  height: 53px;
  top:0px;
  position: relative;;
  float: left;
}
.title-box{
  font-size: 20px;
  text-align: left;
  color: #fff;
}
.percent{
  position:absolute;
  display:inline-block;
}
.bar{
  width: 100%;
  height: 50px;
  background: #A93650;
  position: relative;
  color: #fff;
}
.bar__percent {
  position: absolute;
  z-index: 1;
  background-color: #fd1c56;
  height: 100%;
}
.bar__content {
  width: 100%;
  height: 100%;
  float: left;
  overflow: hidden;
  position: absolute;
  z-index: 2;
}
.bar__content-txt-one {
  /* background: yellow; */
  position: absolute;
  left: 6px;
  font-size: 18px;
  /* margin: 30px 10px 0; */
}
.bar__content-txt-percent{
  position: absolute;
  font-size: 18px;
  margin: 30px 10px 0;
  top: -5px;
  font-weight: lighter;
  opacity: 0.8;
}
.bar__content-txt-two {
  /* background: cyan; */
  position: absolute;
  right: 50px;
  font-size: 18px;
  margin: 30px 10px 0;
  font-weight: 200;
  font-style: normal;
  top: -5px;
}
.bar__image {
  width: 50px;
  height: 100%;
  margin-left: 10px;
  position: absolute;
  right: -2px;
  z-index: 2;
  display: inline-block;
  float: right;
  overflow: hidden;
}
.bar__image img {
  /* max-width: 100%;
  height: auto; */
  height: 50px;
  width: 142%;
}



/*Missao*/

.missao-descricao{
  text-align: left;
  padding: 10px 95px
}

strong{
  color:#fd1c56
}

</style>