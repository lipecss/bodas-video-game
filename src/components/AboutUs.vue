<template>
  <div>
    <section class="the-brides padding-top-100px padding-bottom-130px background-second-color section-ba-1">
      <div class="container">
        <div class="row">
          <div class="col-lg-6">
            <div class="bride-item layout-1 left">
              <div class="line">
                <i class="fa fa-heart-o box-shadow"></i>
              </div>
              <div class="img_in">
                <img src="/imgs/felipecss.jpg" alt="" width="200" height="200">
              </div>
              <div class="content">
                <h2 class="name">Felipecss</h2>
                <div class="description">
                  Player 1
                  <img src="imgs/game-controller.svg" alt="" width="60" height="60">
                </div>
                <ul class="social-media">
                  <li>
                    <a class="instagram" href="https://www.instagram.com/felipecss/">
                      <i class="fa fa-instagram"></i>
                    </a>
                  </li>
                  <li>
                    <a class="twitter" href="https://twitter.com/felipecss">
                      <i class="fa fa-twitter"></i>
                    </a>
                  </li>
                  <li></li>
                </ul>
              </div>
            </div>
          </div>

          <div class="col-lg-6">
            <div class="bride-item layout-1 right">
              <div class="img_in">
                <img src="/imgs/vidaprofile.jpeg" alt="" width="200" height="200">
              </div>

              <div class="content">
                <h2 class="name">Vida (Tatiana)</h2>
                <div class="description">
                  Player 2
                  <img src="/imgs/game-controller.svg" alt="" width="60" height="60">
                </div>
                <ul class="social-media">
                  <li>
                    <a class="instagram" href="https://www.instagram.com/tatiana_crivelaro/">
                      <i class="fa fa-instagram"></i>
                    </a>
                  </li>
                  <li>
                    <a class="twitter" href="#">
                      <i class="fa fa-twitter"></i>
                    </a>
                  </li>
                  <li></li>
                </ul>
              </div>

            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>

ul {
  list-style: none;
}

.fa {
    display: inline-block;
    font: normal normal normal 14px/1 FontAwesome;
    font-size: inherit;
    text-rendering: auto;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}

.row {
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    margin-right: -15px;
    margin-left: -15px;
}

.container {
  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
}

.section-ba-1 {
    position: relative;
}
.padding-bottom-130px {
    padding-bottom: 130px;
}
.padding-top-100px {
    padding-top: 100px;
}
.background-second-color {
    background-color: #fd1c56;
}
.section-ba-1 {
    background-color: #fd1c56;
}

.bride-item.layout-1.left {
    margin-right: 300px;
    text-align: right;
    position: relative;
}
.bride-item.layout-1.right {
    margin-left: 300px;
}

/*Linha */


.bride-item.layout-1.left .line {
    height: 320px;
    width: 1px;
    background-color: rgba(255, 255, 255, 0.3);
    position: absolute;
    right: -315px;
    top: -40px;
}

.bride-item.layout-1.left .line .fa {
    display: block;
    color: #fff;
    background-color: #a93673;
    padding: 8px;
    width: 40px;
    margin-top: 135px;
    margin-left: -18px;
    text-align: center;
    font-size: 20px;
    border-radius: 50%;
    border: 1px solid rgba(255, 255, 255, 0.2);
    margin-right: 6px;
}

/*IMGS */

.bride-item.layout-1.left .img_in {
    width: 220px;
    border-radius: 50%;
    border: 10px solid rgba(255, 255, 255, 0.2);
    margin-right: -260px;
    float: right;
}

.bride-item.layout-1.right .img_in {
    width: 220px;
    border-radius: 50%;
    border: 10px solid rgba(255, 255, 255, 0.2);
    margin-left: -260px;
    float: left;
}

.bride-item.layout-1.left .img_in img {
    border-radius: 50%;
}

.bride-item.layout-1.right .img_in img {
    border-radius: 50%;
}
img {
    max-width: 100%;
}
img {
    vertical-align: middle;
    border-style: none;
}

/*Content */

  /*Left*/
.bride-item.layout-1.left ul.social-media li {
    display: inline-block;
}

.bride-item.layout-1.left .content {
    padding: 55px 0px;
}

.bride-item.layout-1.left h2.name {
    font-size: 22px;
    color: #fff;
    margin-bottom: 0px;
    font-weight: 700;
}
  /*Description*/
.bride-item.layout-1.left .discription {
    font-size: 15px;
    color: #fff;
    margin-bottom: 15px;
    font-weight: 500;
}
  /*Social*/
.bride-item.layout-1.left ul.social-media li a {
    display: block;
    color: #fff;
    padding: 3px;
    width: 35px;
    text-align: center;
    font-size: 20px;
    border-radius: 50%;
    border: 2px solid #fff;
    margin-right: 6px;
}

  /*Right*/
.bride-item.layout-1.right ul.social-media li {
    display: inline-block;
}
.bride-item.layout-1.right .content {
    padding: 55px 0px;
}
.bride-item.layout-1.right h2.name {
    font-family: "Merienda", cursive;
    font-size: 22px;
    color: #fff;
    margin-bottom: 0px;
    font-weight: 700;
}
.bride-item.layout-1.right .discription {
    font-size: 15px;
    color: #fff;
    margin-bottom: 15px;
    font-weight: 500;
}
.bride-item.layout-1.right ul.social-media {
    margin: 0px;
    padding: 0px;
}
.bride-item.layout-1.right ul.social-media li a {
  display: block;
  color: #fff;
  padding: 3px;
  width: 35px;
  text-align: center;
  font-size: 20px;
  border-radius: 50%;
  border: 2px solid #fff;
  margin-right: 6px;
}

@media only screen and (max-width: 600px) {
  .bride-item.layout-1.left .line {
    height: 320px;
    width: 1px;
    background-color: rgba(255, 255, 255, 0.3);
    position: absolute;
    right: -285px;
    top: -40px;
  }
  .bride-item.layout-1.left .img_in {
    width: 220px;
    border-radius: 50%;
    border: 10px solid rgba(255, 255, 255, 0.2);
    margin-right: -285px;
    float: right;
  }
  .bride-item.layout-1.left .line {
    height: 235px;
    width: 2px;
    background-color: rgba(255, 255, 255, 0.3);
    position: absolute;
    right: -293px;
    top: 83px;
  }
  .bride-item.layout-1.right {
    margin-left: 251px;
  }
}


</style>




