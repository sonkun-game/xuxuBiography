<template>
  <div class="container-fluid no_padding">

    <!-- Follow me !! -->
    <!-- <div class="social"></div> -->

    <!-- Slider Section -->
    <div class="container-fluid no_padding" id="carousel">
      <nav class="header">
        <div class="item first">
          xuxubiography
        </div>
        <div class="item second">
          <div class="header_section" @click="scrollToEl('#carousel', { duration: 1000 })">Home</div>
          <div class="header_section" @click="scrollToEl('#portfolio', { duration: 1000 })">Portfolio</div>
          <div class="header_section" @click="scrollToEl('#about', { duration: 1000 })">About</div>
          <div class="header_section" @click="scrollToEl('#blog', { duration: 1000 })">Blog</div>
          <div class="header_section" @click="scrollToEl('#insta', { duration: 1000 })">Insta</div>
          <div class="header_section" @click="scrollToEl('#testimonal', { duration: 1000 })">Testimonial</div>
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
    <div class="container-fluid about" id="about">
      <div class="left_description">
        <div class="m-auto">
          <h1 class="description_header">
            Hi there, my name Xu and I love photography
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
    <div class="photo container-fluid no_padding" id="portfolio">

      <div class="image_cover" id="image_cover">
        <div class="image_cover_title">
          <span>Xu Xu Beauty</span>
          <h1>Image Shot</h1>
        </div>
      </div>

      <div class="row photo_row">
        <div class="image_item" v-for="image, index in gallery" @mouseover="onHoverPhoto($event, Math.floor(index / 3))"
          @click="showImage(image)" :key="image.id">
          <img class="w-100" :src="image.url" alt="Gallery Image">
        </div>
      </div>

      <div v-if="selectedImage" class="modal">
        <img :src="selectedImage.url" alt="Selected Image" @click="hideImage" />
      </div>

    </div>

    <!-- Poster  -->
    <div class="poster container-fluid" id="blog">
      <div class="poster-header">
        Xu Xu Fashion
      </div>
      <div class="poster-body">

        <div class="card">
          <img src="@/assets/img/img28.jpg" alt="Poster Image" />
          <div class="card-body">
            <h2 class="card-title">Xu Xu Photo</h2>
            <p class="card-text">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque
              laudantium, totam rem aperiam, eaque ipsa quae.</p>
          </div>
        </div>
        <div class="card">
          <img src="@/assets/img/img31.jpg" alt="Poster Image" />
          <div class="card-body">
            <h2 class="card-title">Xu Xu Photo</h2>
            <p class="card-text">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque
              laudantium, totam rem aperiam, eaque ipsa quae.</p>
          </div>
        </div>
        <div class="card">
          <img src="@/assets/img/img34.jpg" alt="Poster Image" />
          <div class="card-body">
            <h2 class="card-title">Xu Xu Photo</h2>
            <p class="card-text">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque
              laudantium, totam rem aperiam, eaque ipsa quae.</p>
          </div>
        </div>

      </div>
    </div>

    <!-- Testimonial -->
    <div class="testimonial" id="testimonal">
      <div id="testimonial" class="carousel slide" data-ride="carousel">

        <!-- Wrapper for slides -->
        <div class="carousel-inner">
          <div class="carousel-item active">
            <div class="image_slider_2">
              <div class="top_caption">Testimonial</div>
              <div class="slider_paragraph_title">
                <h3>
                  <span>"Anh thích những tấm ảnh của em"</span>
                </h3>
                <div class="slider_comment">
                  <img src="@/assets/logo3.jpg" class="slider_comment_avatar rounded-circle" alt="Son image" />
                </div>
                <div class="small_text">
                  Hoang Son, The Software Developer
                </div>
              </div>
            </div>
          </div>
          <div class="carousel-item">
            <div class="image_slider_2">
              <div class="top_caption">Testimonial</div>
              <div class="slider_paragraph_title">
                <h3>
                  <span>"Anh thích con người em"</span>
                </h3>
                <div class="slider_comment">
                  <img src="@/assets/logo3.jpg" class="slider_comment_avatar rounded-circle" alt="Son image" />
                </div>
                <div class="small_text">
                  Hoang Son, The Software Developer
                </div>
              </div>
            </div>
          </div>
          <div class="carousel-item">
            <div class="image_slider_2">
              <div class="top_caption">Testimonial</div>
              <div class="slider_paragraph_title">
                <h3>
                  <span>"Chúc mừng sinh nhật em 🎂, hi vọng em luôn mỉm cười mỗi ngày"</span>
                </h3>
                <div class="slider_comment">
                  <img src="@/assets/logo3.jpg" class="slider_comment_avatar rounded-circle" alt="Son image" />
                </div>
                <div class="small_text">
                  Hoang Son, The Software Developer
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Left and right controls -->
        <a class="carousel-control-prev" href="#testimonial" data-slide="prev">
          <span><i class="fa-solid fa-chevron-left Fs24"></i></span>
          <span class="sr-only">Previous</span>
        </a>
        <a class="carousel-control-next" href="#testimonial" data-slide="next">
          <span><i class="fa-solid fa-chevron-right Fs24"></i></span>
          <span class="sr-only">Next</span>
        </a>
      </div>
    </div>

    <!-- Infinite Loop -->
    <div id="insta" class="image-container" ref="imageContainer" @mousedown="startDrag" @mousemove="drag"
      @mouseup="endDrag" @mouseleave="endDrag">
      <div class="insta-header">
        Follow my instagram for more ^^
      </div>

      <div class="image-list">
        <div>
          <img src="@/assets/square_img_300/img1.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img2.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img3.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img4.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img5.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img6.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img7.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img8.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img9.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img10.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img11.jpg" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
      </div>
    </div>

    <!-- Scroll to top button -->
    <button class="scroll-to-top" @click="scrollToTop()">
      <i class="fa-solid fa-chevron-up"></i>
    </button>
  </div>
</template>


<script>
import vueScrollTo from 'vue-scrollto';

window.onload = function () {
  window.scrollTo(0, 0);
  setInterval(function () {
    window.scrollBy(-1, 0);
  }, 10);
};

export default {

  data() {
    return {
      gallery: [
        { id: 1, url: require('@/assets/img/img44.jpg') },
        { id: 2, url: require('@/assets/img/img45.jpg') },
        { id: 3, url: require('@/assets/img/img55.jpg') },
        { id: 4, url: require('@/assets/img/img5.jpg') },
        { id: 5, url: require('@/assets/img/img25.jpg') },
        { id: 6, url: require('@/assets/img/img26.jpg') },
      ],
      selectedImage: null,
      // For infinite loop
      isDragging: false,
      startPosition: 0,
      currentScrollLeft: 0,
      velocity: 0,
      lastTime: 0,
      animationFrameId: null,
      showScrollButton: true,
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
      var element_height = 558 * row;
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
    },
    startDrag(event) {
      this.isDragging = true;
      this.startPosition = event.clientX;
      this.startScrollLeft = this.$refs.imageContainer.scrollLeft;
      this.velocity = 0;
      this.lastTime = performance.now();
      cancelAnimationFrame(this.animationFrameId);
    },
    drag(event) {
      if (this.isDragging) {
        const delta = event.clientX - this.startPosition;
        const currentTime = performance.now();
        const timeDelta = currentTime - this.lastTime;
        this.velocity = delta / timeDelta;
        this.$refs.imageContainer.scrollLeft = this.startScrollLeft - delta;
        this.lastTime = currentTime;
      }
    },
    endDrag() {
      this.isDragging = false;
      this.animationFrameId = requestAnimationFrame(this.decelerate);
    },
    decelerate() {
      if (Math.abs(this.velocity) > 0.1) {
        this.$refs.imageContainer.scrollLeft -= this.velocity;
        this.velocity *= 0.95;
        this.animationFrameId = requestAnimationFrame(this.decelerate);
      }
    },
    stopAnimation() {
      cancelAnimationFrame(this.animationFrameId);
    },
    scrollToTop() {
      vueScrollTo.scrollTo('#carousel', { duration: 1500 });
    },
    scrollToEl(id) {
      vueScrollTo.scrollTo(id, { duration: 1000 });
    }
  },
  beforeUnmount() {
    this.stopAnimation();
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
@import url('@/assets/css/infinite_slider.css');
@import url('@/assets/css/social.css');
@import url('@/assets/css/scrollToTop.css');
@import url('@/assets/css/mobile.css');

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

* {
  -webkit-user-drag: none;
  user-select: none;
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
}

.blank_space {
  width: 100%;
  height: 200px;
  background-color: white;
}
</style>


