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

    <div class="image_cover" id="image_cover">
      <div class="image_cover_title">
        <span>Hue Hue Beauty</span>
        <h1>Image Shot</h1>
      </div>
    </div>

    <div class="row photo_row">
      <div class="image_item" v-for="image,index in gallery" 
        @mouseover ="onHoverPhoto($event, Math.floor(index/3))"
        @click="showImage(image)"
       :key="image.id">
        <img class="w-100" :src="image.url" alt="Gallery Image">
      </div>
    </div>

    <div v-if="selectedImage" class="modal">
      <img :src="selectedImage.url" alt="Selected Image" @click="hideImage" />
    </div>

  </div>

  <!-- Poster  -->
  <div class="poster container-fluid">
    <div class="poster-header">
      I do for you
    </div>
    <div class="poster-body">

      <div class="card">
        <img src="@/assets/img/img28.jpg" alt="Poster Image" />
        <div class="card-body">
          <h2 class="card-title">Hue Hue Photo</h2>
          <p class="card-text">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae.</p>
        </div>
      </div>
      <div class="card">
        <img src="@/assets/img/img31.jpg" alt="Poster Image" />
        <div class="card-body">
          <h2 class="card-title">Hue Hue Photo</h2>
          <p class="card-text">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae.</p>
        </div>
      </div>
      <div class="card">
        <img src="@/assets/img/img34.jpg" alt="Poster Image" />
        <div class="card-body">
          <h2 class="card-title">Hue Hue Photo</h2>
          <p class="card-text">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae.</p>
        </div>
      </div>

    </div>
  </div>

  <!-- Testimonial -->
  <div class="testimonial">

  </div>
</template>

<script>

window.onload = function() {
  // Set scroll position to left on page load
  window.scrollTo(0, 0);

  // Continuously scroll left
  setInterval(function() {
    window.scrollBy(-1, 0); // Adjust the values as per your preference
  }, 10); // Adjust the scroll speed as per your preference
};

export default {
  data() {
    return {
      gallery: [
        { id: 1, url: require('@/assets/img/img44.jpg') },
        { id: 2, url: require('@/assets/img/img45.jpg') },
        { id: 3, url: require('@/assets/img/img39.jpg') },
        { id: 4, url: require('@/assets/img/img5.jpg') },
        { id: 5, url: require('@/assets/img/img25.jpg') },
        { id: 6, url: require('@/assets/img/img26.jpg') },
      ],
      selectedImage: null
    }
  },
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
    onHoverPhoto(event, row = 0) {
      var element = event.target; 
      var rect = element.getBoundingClientRect();
      var x = rect.left;
      var element_height = rect.height * row;
      var currentLeft = parseInt(x) || 0;
      // calculate the chosen Image


      document.getElementById("image_cover").style.left = currentLeft + 'px';
      document.getElementById("image_cover").style.top = element_height + 'px';
    },
    getGalleryRow() {
      return Math.ceil(this.gallery.length / 3);
    },
    showImage(image) {
      console.log('show image !');
      this.selectedImage = image;
    },
    hideImage() {
      this.selectedImage = null;
    }
  }
}
</script>

<style>
@import url('@/assets/css/font.css');
@import url('@/assets/css/about.css');
@import url('@/assets/css/photo.css');
@import url('@/assets/css/header.css');
@import url('@/assets/css/slider.css');
@import url('@/assets/css/poster.css');
@import url('@/assets/css/testimonial.css');


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


.no_padding {
  padding: 0 !important;
}



</style>


