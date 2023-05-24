<template>
  <!-- Slider Section -->
  <div class="container-fluid no_padding">
    <nav class="hue-header">
      <div class="item first">
        huehuebiography
      </div>
      <div class="item second">
        <div class="header_section">Home</div>
        <div class="header_section">Portfolio</div>
        <div class="header_section">Service</div>
        <div class="header_section">About</div>
        <div class="header_section">Blog</div>
        <div class="header_section">Contact</div>
      </div>
      <div class="item third">
        <i class="fa-brands fa-facebook"></i>
        <i class="fa-brands fa-instagram"></i>
        <i class="fa-brands fa-tiktok"></i>
        <i class="fa-brands fa-youtube"></i>
      </div>
    </nav>
    <!-- carousel use 2158px image-->
    <div id="myCarousel" class="carousel slide" data-ride="carousel">
      <!-- Indicators -->
      <ol class="carousel-indicators">
        <li data-target="#myCarousel" data-slide-to="0" class="active"></li>
        <li data-target="#myCarousel" data-slide-to="1"></li>
        <li data-target="#myCarousel" data-slide-to="2"></li>
      </ol>

      <!-- Wrapper for slides -->
      <div class="carousel-inner">
        <div class="carousel-item active">
          <div class="image_slider">
            <img class="slide_item w-100" src="./assets/slide/slide0.jpg" alt="First slide">
            <div class="slider_title">
              <span class="small_text">Action Shot</span>
              <h1>Nature of beauty</h1>
            </div>
          </div>
        </div>
        <div class="carousel-item">
          <div class="image_slider">
            <img class="slide_item w-100" src="./assets/slide/slide1.jpg" alt="Second slide">
            <div class="slider_title">
              <span class="small_text">Action Shot</span>
              <h1>Nature of beauty</h1>
            </div>
          </div>
        </div>
        <div class="carousel-item">
          <div class="image_slider">
            <img class="slide_item w-100" src="./assets/slide/slide3.jpg" alt="Third slide">
            <div class="slider_title">
              <span class="small_text">Action Shot</span>
              <h1>Nature of beauty</h1>
            </div>
          </div>
        </div>
      </div>

      <!-- Left and right controls -->
      <a class="carousel-control-prev" href="#myCarousel" data-slide="prev">
        <span class="glyphicon glyphicon-chevron-left"></span>
        <span class="sr-only">Previous</span>
      </a>
      <a class="carousel-control-next" href="#myCarousel" data-slide="next">
        <span class="glyphicon glyphicon-chevron-right"></span>
        <span class="sr-only">Next</span>
      </a>
    </div>
  </div>

  <!-- About -->
  <div class="container-fluid about">
    <div class="left_description">
      <div class="m-auto">
        <h1 class="description_header">
          Hi there, my name Hue and I love photography
        </h1>
        <p>
          Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem
          aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta.
        </p>
      </div>
    </div>
    <div class="about_img">
      <img class="w-100" src="./assets/img/img41.jpg" alt="First slide">
    </div>
    <div class="right_description">
      <div class="m-auto">
        <p>I'm </p>
        <h1 class="description_number">
          23
        </h1>
        <p>Years old</p>
        <p>
          Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem
          aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta.
        </p>
        <button type="button" class="btn btn-outline-success">
          Hey, checkout my photo
        </button>
      </div>
    </div>
  </div>

  <!-- Photo -->
  <div class="photo container-fluid no_padding">

    <div class="image_cover" id="image_cover"></div>

    <!-- row 1 -->
    <div class="row">
      <div class="image_item" @mouseover ="onHoverPhoto($event)">
        <img class="w-100" src="./assets/img/img11.jpg" alt="First slide">
      </div>
      <div class="image_item" @mouseover ="onHoverPhoto($event)">
        <img class="w-100" src="./assets/img/img12.jpg" alt="First slide">
      </div>
      <div class="image_item">
        <img class="w-100" src="./assets/img/img13.jpg" alt="First slide">
      </div>
    </div>

    <!-- row 2 -->
    <div class="row">
      <div class="image_item">
        <img class="w-100" src="./assets/img/img5.jpg" alt="First slide">
      </div>
      <div class="image_item">
        <img class="w-100" src="./assets/img/img25.jpg" alt="First slide">
      </div>
      <div class="image_item">
        <img class="w-100" src="./assets/img/img26.jpg" alt="First slide">
      </div>
    </div>

  </div>
</template>

<script>

export default {
  name: 'App',
  head: {
    link: [
      {
        rel: "icon",
        href: require("./assets/logo1.jpg")
      },
    ]
  },
  methods: {
    onHoverPhoto(event) {
      var element = event.target;
      var rect = element.getBoundingClientRect();
      var x = rect.left;
      var y = rect.top;
      var currentLeft = parseInt(x) || 0;
      var currentTop = parseInt(y) || 0;
      document.getElementById("image_cover").style.left = currentLeft + 'px';
      document.getElementById("image_cover").style.top = currentTop + 'px';
    }
  }
}
</script>

<style>
/* font face */
@font-face {
  font-family: Jost;
  src: url('./assets/font/Jost/Jost-VariableFont_wght.ttf');
}

@font-face {
  font-family: MotherTongue;
  src: url('./assets/font/mother-tongue-personal-use-font/MotherTonguePersonalUse-x3L3m.otf');
}

@font-face {
  font-family: WildCrazy;
  src: url('./assets/font/wildcrazy-font/Wildcrazy-WKYO.ttf');
}

@font-face {
  font-family: PoiretOne;
  src: url('./assets/font/Poiret_One/PoiretOne-Regular.ttf');
}

.btn {
  font-family: 'Jost', sans-serif;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


/* Header CSS -------------------------------------------> */
.hue-header {
  z-index: 9;
  position: absolute;
  top: 0;
  height: 80px;
  width: 100%;
  border-bottom: 0.5px lightgray solid;
  background: linear-gradient(180deg, rgba(0, 0, 0, 1) 0%, rgba(255, 255, 255, 0) 100%);
  /* font */
  font: 'Jost', sans-serif;
  color: white;
  /* flex style */
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 0px 15px 0px 15px;
}

.hue-header .item {
  display: flex;
  align-items: center;
  justify-content: center;
}

.hue-header .item.first {
  justify-self: left;
  font-family: 'WildCrazy', sans-serif;
  font-size: 24px;
}

.hue-header .item.second {
  justify-self: center;
  font-size: 14px;
}

.hue-header .item.third {
  justify-self: right;
  font-size: 18px;
}

.hue-header .item.third i {
  width: 40px;
  cursor: pointer;
}

.header_section {
  width: 100px;
  height: 100%;
  cursor: pointer;
  /* center text */
  display: flex;
  align-items: center;
  justify-content: center;
  /* effect */
  border-bottom: 3px solid transparent;
  transition: border-bottom-color 1s;
}

.header_section::after {
  content: '';
  position: absolute;
  bottom: 0;
  width: 0;
  height: 3px;
  background-color: white;
  transition: width 1s;
}

.header_section:hover::after {
  width: 100px;
}

/* icon color */
.fa-facebook:hover {
  color: #17A9FD;
}

.fa-instagram:hover {
  color: #feda75;
}

.fa-tiktok:hover {
  color: #010101;
}

.fa-youtube:hover {
  color: #c4302b;
}

/* Header CSS -------------------------------------------> */


.no_padding {
  padding: 0 !important;
}

/* Slider -----------------------------------------------> */
.image_slider {
  height: 729px;
}

.slide_item {
  position: relative;
  top: -20vh;
}

.slider_title {
  width: 100%;
  font-family: PoiretOne;
  position: absolute;
  bottom: 5vh;
  color: white;
}

.slider_title .small_text {
  font-family: 'Jost', sans-serif;
  font-size: 20px;
}

/* About ----------------------------------------------> */
.about {
  position: relative;
  color: black;
  display: flex;
  flex-direction: row;
  justify-content: center;
  padding-top: 110px;
  padding-bottom: 110px;
}

.about_img {
  max-width: 35%;
  padding-left: 15px;
  padding-right: 15px;

}

.left_description,
.right_description {
  max-width: 25%;
  font-family: 'PoiretOne', sans-serif;
  text-align: left;
  display: flex;
}

.left_description p,
.right_description p {
  font-size: 18px;
  font-weight: 500;
}

.description_header {
  font-weight: 500;
  padding-bottom: 15px;
}

.description_number {
  font-size: 130px;
}

/* Photo style ----------------------------------> */
.photo {
  position: relative;
}

.image_item {
  position: relative;
  max-width: 33%;
  background-color: black;
}

.image_cover {
  position: absolute;
  top: 0;
  left: 0;
  width: 33.8%;
  height: 50%;
  cursor: pointer;
  display: block;
  z-index: 1;
  background: linear-gradient(0deg, rgba(0, 0, 0, 1) 0%, rgba(255, 255, 255, 0) 100%);
  transition: 0.5s;
}
</style>


