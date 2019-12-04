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
            <div class="col-md-12 ">
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
          <div class="row content-table">
            <div class="col-md-12 table">
              <div class="full-width bg-grad">
                <h2 class="categoryHeading">
                      Jogador
                </h2>
              </div>
              <h6 @mouseover="hoverHouse = true" @mouseout="hoverHouse = false" id="career-info-safehouse" class="far fa-question-circle"></h6>
              <div v-if="hoverHouse" id="career-info-safehouse-info">
                <h4>Visite a Safe House de cada Jogador aos Finais de Semana</h4>
                <p>Se precisar saber do caminho. Utilize o mapa e ache a melhor rota.</p>
              </div>
              <img id="career-safehouse" src="https://s.rsg.sc/sc/images/games/GTAV/career/overview/safehouse/default.png">
              <img id="career-controller" src="/imgs/XboxOneController.png">
              <img id="career-radio" src="https://cdn141.picsart.com/266073716030212.png">
              <div v-if="hoverMusic" id="career-info-radio-info">
                <h4>Música preferida do Casal</h4>
                <p>Jorge e Mateus - Pra Sempre com Você</p>
              </div>
              <div class="notes">
                <img id="note" src="/imgs/note1.png" alt="">
                <img id="note2" src="/imgs/note1.png" alt="">
                <div id="career-spending">
                  <table id="career-spending-table">
                    <tbody>
                      <tr class="total">
                        <td>Terefas diárias</td>
                        <td class="val">Pontos</td>
                      </tr>
                      <tr>
                        <td>Ligar para o Amor</td>
                        <td class="val">100</td>
                      </tr>
                      <tr>
                        <td>Usar Trapaças</td>
                        <td class="val">0</td>
                      </tr>
                      <tr>
                        <td>Perguntar "como está?"</td>
                        <td class="val">50</td>
                      </tr>
                      <tr>
                        <td>Esperar chegar em casa</td>
                        <td class="val">10</td>
                      </tr>
                      <tr>
                        <td>Dizer "Eu te amo"</td>
                        <td class="val">1000</td>
                      </tr>
                      <tr>
                        <td>Jogar em modo Co-op</td>
                        <td class="val">200</td>
                      </tr>
                      <tr>
                        <td>Viverem Felizes e em Armônia</td>
                        <td class="val">2000</td>
                      </tr>
                      <tr>
                        <td>Lotar as mensagens de emojis</td>
                        <td class="val">60</td>
                      </tr>
                      <tr>
                        <td><strong>On</strong> (juntos) a semana inteira</td>
                        <td class="val">0</td>
                      </tr>
                      <tr>
                        <td> </td>
                      </tr>
                      <tr class="total">
                        <td>Total de Pontos</td>
                        <td class="val">3410</td>
                      </tr>
                    </tbody>
                  </table>
                </div>
              </div>
            </div>
            <h6 @mouseover="hoverMusic = true" @mouseout="hoverMusic = false" id="career-info-radio" class="far fa-question-circle"></h6>
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
      hoverMusic: false,
      hoverHouse: false,
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
        "img": "imgs/vida25.jpg"
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
        "name": "Vejam um filme bizzaro no 1 econtro",
        "progress": 100,
        "trofeus": 300,
        "img": "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTodRr-MpQXfQN1oiATQDGJLrCWly-13yIPbNNikCTf3JgA9ENL"
        },
        12:{
        "name": "Casa Própria",
        "progress": 0,
        "trofeus": 10000,
        "img": "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTEPPfIb-9_qc2wwlt8426eCLjx1nYKKF8FLnpt0aCkGyjnGIZ_"
        },
        13:{
        "name": "Tenha a Digital de ambos nos celulares",
        "progress": 100,
        "trofeus": 100,
        "img": "https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQ1F2ime0G0in72laSRUsA5YIWrb1-IxuDupmFLf8qt1pYtE7Kw"
        },
        15:{
        "name": "O Grande Dia (Casamento)",
        "progress": 0,
        "trofeus": 10000,
        "img": "imgs/vida22.jpg"
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

/*TABLE */

.table{
  background: url(/imgs/mesa.jpeg);
  position: relative;
  height: 462px;
  border-radius: 10px;
}
#career-safehouse {
  position: absolute;
  top: -40px;
  left: 419px;
  max-width: 100%;
  width: 28%;
}
#career-controller {
  position: absolute;
  top: 281px;
  left: 400px;
  max-width: 100%;
  width: 29%;
  transform: rotate(21deg);
}
#note {
  position: absolute;
  top: 59px;
  left: -50px;
  width: 418px;
  z-index: 10;
}
#note2 {
  position: absolute;
  top: 75px;
  left: 18px;
  width: 361px;
  z-index: 09;
  transform: rotate(9deg);
}
#career-spending {
  position: absolute;
  top: 30px;
  left: -1px;
  color: #000;
  width: 410px;
  height: 296px;
  background-repeat: no-repeat;
  padding: 70px 40px;
  z-index: 100;
  font-size: 11px;
  transform: rotate(-4deg);
  font-family: chalet-london-sixty, sans-serif;
}
#career-spending-table td.val {
  text-align: right;
}
#career-spending-table td {
  width: 83%;
  padding: 0;
  border-bottom: 1px dotted #ccc;
  line-height: 16px;
}
#career-spending-table tr.total td {
    color: red;
    font-weight: 700;
}
#career-radio {
  position: absolute;
  left: 75px;
  top: 308px;
  z-index: 100;
  transform: rotate(-7deg);
  width: 25%;
}

#career-info-radio {
  position: absolute;
  top: 729px;
  left: 180px;
  z-index: 100;
  color: #fff
}

#career-info-radio-info {
  position: absolute;
  top: 335px;
  left: 109px;
  color: #fff;
  background: linear-gradient(to bottom,#000,rgba(0,0,0));
  z-index: 100;
  border: 1px solid black;
  padding: 9px;
}

#career-info-radio-info h4{
  color: yellow;
}

#career-info-safehouse {
  position: absolute;
  left: 456px;
  top: 74px;
  z-index: 1000;
  color: #fff;
}

#career-info-safehouse-info {
  position: absolute;
  top: 105px;
  left: 250px;
  color: #fff;
  background: linear-gradient(to bottom,#000,rgba(0,0,0));
  z-index: 1000;
  border: 1px solid black;
  padding: 9px;
}

#career-info-safehouse-info h4{
  font-size: 21px;
  color: yellow;
}

.bg-grad {
  /* background: -webkit-linear-gradient(top,#000,rgba(0,0,0)); */
  background: linear-gradient(to bottom,#000,rgba(0,0,0));
  color: #fff
}
.full-width {
  margin: 0px -16px 8px;
  padding: 10px 18px;
}

@media only screen and (max-width: 600px) {
  .content-table {
    position: relative;
    width: 336px;
    left: -67px;;
  }
  .bar__content-txt-one {
    position: absolute;
    left: 6px;
    font-size: 15px;
  }

  #note{
    position: absolute;
    top: 59px;
    left: -50px;
    width: 294px;
    height: 356px;
    z-index: 10;
  }

  #note2 {
    display: none;
  }

  #career-spending {
    position: absolute;
    top: 28px;
    left: -29px;
    color: #000;
    width: 236px;
    height: 267px;
    background-repeat: no-repeat;
    padding: 70px 40px;
    z-index: 100;
    font-size: 10px;
    -webkit-transform: rotate(-4deg);
    transform: rotate(-4deg);
    font-family: chalet-london-sixty, sans-serif;
  }

  #career-radio {
      position: absolute;
      left: 42px;
      top: 365px;
      z-index: 100;
      -webkit-transform: rotate(-7deg);
      transform: rotate(-7deg);
      width: 30%;
  }

  #career-info-radio {
    position: absolute;
    top: 378px;
    left: 38px;
    z-index: 100;
    color: #fff;
  }

  #career-info-radio-info {
    position: absolute;
    top: 285px;
    left: 56px;
    color: #fff;
    background: linear-gradient(to bottom,#000,rgba(0,0,0));
    z-index: 1000;
    border: 1px solid black;;
  }

  #career-safehouse {
    position: absolute;
    top: -17px;
    left: 182px;
    max-width: 100%;
    width: 41%;
  }

  #career-info-safehouse {
    position: absolute;
    left: 202px;
    top: 74px;
    z-index: 1000;
    color: #fff;
  }

  #career-info-safehouse-info {
    position: absolute;
    top: 105px;
    left: 5px;
    width: 350px;
    font-size: 15px;
    color: #fff;
    background: linear-gradient(to bottom,#000,rgba(0,0,0));
    z-index: 1000;
    border: 1px solid black;
  }

  #career-controller {
    position: absolute;
    top: 281px;
    left: 217px;
    max-width: 100%;
    width: 29%;
    -webkit-transform: rotate(21deg);
    transform: rotate(21deg);
  }
}

@media only screen and (max-width: 750px) {


}
</style>