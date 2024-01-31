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
              <!-- <div class="slider_title">
                <span class="small_text">Action Shot</span>
                <h1>Nature of beauty</h1>
              </div> -->
            </div>
          </div>
          <div class="carousel-item">
            <div class="image_slider">
              <img class="slide_item w-100" src="./assets/slide/slide1.jpg" alt="Second slide">
              <!-- <div class="slider_title">
                <span class="small_text">Action Shot</span>
                <h1>Nature of beauty</h1>
              </div> -->
            </div>
          </div>
          <div class="carousel-item">
            <div class="image_slider">
              <img class="slide_item w-100" src="./assets/slide/slide2.jpg" alt="Third slide">
              <!-- <div class="slider_title">
                <span class="small_text">Action Shot</span>
                <h1>Nature of beauty</h1>
              </div> -->
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
            Hi there, This is my page for me and my boyfriend
          </h1>
          <p>
            Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem
            aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta.
          </p>
        </div>
      </div>
      <div class="about_img">
        <img class="w-100" src="./assets/img/img41.png" alt="First slide">
      </div>
      <div class="right_description">
        <div class="m-auto">
          <p>We had love for </p>
          <h1 class="description_number">
            {{ calculateLoverDate }}
          </h1>
          <p>Days</p>
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

      <div class="image_cover" id="image_cover" style="display: none;">
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
          <img src="@/assets/poster/img01.jpg" alt="Poster Image" />
          <div class="card-body">
            <h2 class="card-title">Xu Xu Photo</h2>
            <p class="card-text">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque
              laudantium, totam rem aperiam, eaque ipsa quae.</p>
          </div>
        </div>
        <div class="card">
          <img src="@/assets/poster/img02.jpg" alt="Poster Image" />
          <div class="card-body">
            <h2 class="card-title">Xu Xu Photo</h2>
            <p class="card-text">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque
              laudantium, totam rem aperiam, eaque ipsa quae.</p>
          </div>
        </div>
        <div class="card">
          <img src="@/assets/poster/img03.jpg" alt="Poster Image" />
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
                  <span>"Tớ thích cậu"</span>
                </h3>
                <div class="slider_comment">
                  <img src="@/assets/testi/img01.jpg" class="slider_comment_avatar rounded-circle" alt="Son image" />
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
                  <span>"Tớ thích con người cậu"</span>
                </h3>
                <div class="slider_comment">
                  <img src="@/assets/testi/img02.jpg" class="slider_comment_avatar rounded-circle" alt="Son image" />
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
                  <span>"Làm người yêu t nhớ"</span>
                </h3>
                <div class="slider_comment">
                  <img src="@/assets/testi/img03.jpg" class="slider_comment_avatar rounded-circle" alt="Son image" />
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
          <img src="@/assets/square_img_300/img1.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img2.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img3.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img4.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img5.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img6.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img7.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img8.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img9.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img10.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
        <div>
          <img src="@/assets/square_img_300/img11.png" />
          <div class="image-item-cover">
            <i class="fa-brands fa-instagram Fs24"></i>
          </div>
        </div>
      </div>
    </div>

    <!-- Todo -->
    <div id="todo" class="todo">
      <div class="todo-container">
        <div class="todo-header">
          100 list must-to-do things together : {{ calculateDoneList }} / {{ toDoListCount }}
        </div>
        <ul class="todo-ul">
          <li class="todo-list" v-for="(item, index) in todo" :key="index">
            <div v-if="item.done">
              <span style="color: coral">
                <span style="margin-right: 4px; color: coral">{{ index + 1 }}</span><span>{{ item.name }}</span> ❤️
              </span>
            </div>
            <div v-else>
              <span style="margin-right: 4px;">{{ index + 1 }}</span><span>{{ item.name }}</span>
            </div>
          </li>
        </ul>
      </div>
    </div>

    <!-- Plan -->
    <div id="plan">
      <div class="plan-container">
        <div class="plan-header">
          Plan
        </div>
      </div>
      <pre>
        2024
        Mục tiêu :
        trong năm : 2024 : mức lương trên 20
        có 6 múi

        Mục tiêu của Xu iu dấu:
        đạt danh hiệu suất xắc
        và giảm cân

        Mục tiêu chung 2024 :
        + Kiếm nhiều tiền, thăng tiến trong công việc
        - đặt mục tiêu để ra khoảng 10tr/ tháng
        + 2 đứa tiến đến hôn nhân (tháng 10 - 12)

        2025: phải tốt nghiệp thạc sĩ
      </pre>
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
        { id: 1, url: require('@/assets/img/gallery01.jpg') },
        { id: 2, url: require('@/assets/img/gallery02.jpg') },
        { id: 3, url: require('@/assets/img/gallery03.jpg') },
        { id: 4, url: require('@/assets/img/gallery04.jpg') },
        { id: 5, url: require('@/assets/img/gallery05.jpg') },
        { id: 6, url: require('@/assets/img/gallery06.jpg') },
      ],
      todo: [
        {
          name: "Làm hoa cùng nhau",
          done: true
        },
        {
          name: "Nấu ăn cùng nhau",
          done: true
        },
        {
          name: "tắm cùng nhau",
          done: false
        },
        {
          name: "Đi xem phim cùng nhau",
          done: true
        },
        {
          name: "Đi bơi cùng nhau",
          done: false
        },
        {
          name: "Đi tô tượng cùng nhau",
          done: true
        },
        {
          name: "Đạp xe cùng nhau quanh hồ tây",
          done: true
        },
        {
          name: "Đạp vịt cùng nhau",
          done: true
        },
        {
          name: "Đi ăn lẩu cùng nhau",
          done: true
        },
        {
          name: "Đi dã ngoại cùng nhau",
          done: true
        },
        {
          name: "Cùng nhau đi bãi đá sông Hồng và chụp ảnh",
          done: false
        },
        {
          name: "Cùng nhau đi shopping",
          done: true
        },
        {
          name: "Cùng nhau đi chụp ảnh lấy luôn",
          done: true
        },
        {
          name: "Đi nhà ma",
          done: true
        },
        {
          name: "Cùng nhau đi trượt patin",
          done: false
        },
        {
          name: "Cùng nhau gắp thú",
          done: true
        },
        {
          name: "Cùng nhau chơi game",
          done: true
        },
        {
          name: "Cùng nhau mặc đồ đôi",
          done: false
        },
        {
          name: "Netflix and chill",
          done: true
        },
        {
          name: "Massage cho nhau",
          done: true
        },
        {
          name: "Cùng nhau ăn tối lãng mạn",
          done: false
        },
        {
          name: "Cùng nhau đi chơi ở phố đi bộ",
          done: false
        },
        {
          name: "Cùng nhau đi nhậu",
          done: false
        },
        {
          name: "Cùng nhau trao quà noel",
          done: true
        },
        {
          name: "Cùng nhau làm gốm",
          done: true
        },
        {
          name: "Cùng nhau đi thủy cung",
          done: false
        },
        {
          name: "Lên tòa nhà cao nhất Hà Nội",
          done: false
        },
        {
          name: "Cùng nhàu đi nhà tù Hỏa Lò",
          done: false
        },
        {
          name: "Cùng nhàu đi Hoàng Thành Thăng Long, chụp ảnh mặc cổ phục",
          done: false
        },
        {
          name: "Có sáu múi",
          done: false
        },
        {
          name: "Khóa môi từ 5 đến 10 phút",
          done: true
        },
        {
          name: "Đăng ảnh nhau trên insta",
          done: true
        },
        {
          name: "Cùng nhau đi hiệu sách",
          done: true
        },
        {
          name: "Cùng nhau vẽ tranh",
          done: true
        },
        {
          name: "Viết thư tình cho nhau, càng sến càng tốt",
          done: true
        },
        {
          name: "Đút cho nhau ăn, đến khi hết bữa ăn",
          done: true
        },
        {
          name: "Cùng nhau đi nhà thờ",
          done: true
        },
        {
          name: "Cùng nhau đi làm nến thớm",
          done: false
        },
        {
          name: "Cùng nhau đi ăn khoai & ngô nướng vào trời giá rét",
          done: true
        },
        {
          name: "Cùng nhau đi thuyền",
          done: true
        },
        {
          name: "Cùng nhau đi ăn sushi",
          done: true
        },
        {
          name: "Cùng nhau đi xem tarot",
          done: false
        },
        {
          name: "Cùng nhau đi lắp lego",
          done: true
        },
        {
          name: "Cùng nhau đi chùa",
          done: false
        },
        {
          name: "Cùng nhau thức đếm countdown",
          done: true
        },
        {
          name: "Cùng nhau đi cafe nằm",
          done: true
        },
        {
          name: "Cùng nhau đi làm nail",
          done: false
        },
        {
          name: "Cùng nhau đi chơi bowling",
          done: false
        },
        {
          name: "Cùng nhau đi hội chợ( đồ cũ, sự kiện, ...)",
          done: false
        },
        {
          name: "Tỏ tình lần 2",
          done: false
        },
        {
          name: "Cùng nhau chơi game xèng",
          done: true
        },
        {
          name: "Cùng nhau nhảy/ khiêu vũ",
          done: false
        },
        {
          name: "Cùng nhau đi xe đụng/ tàu lượn ở khu vui chơi",
          done: false
        },
        {
          name: "Cùng nhau xem phim kinh dị lúc nửa đêm",
          done: true
        },
        {
          name: "Cùng nhau đi spa làm đẹp",
          done: false
        },
        {
          name: "Cùng nhau đi hát và hát cho nhau nghe",
          done: true
        },
        {
          name: "Cùng nhau đi tập thể dục buổi sáng sớm",
          done: true
        },
        {
          name: "Cùng nhau đi trượt băng",
          done: false
        },
        {
          name: "Cùng nhau làm cocktail",
          done: false
        },
        {
          name: "Sấy tóc cho nhau",
          done: false
        },
        {
          name: "Cùng nhau chơi trò mạo hiểm",
          done: false
        },
        {
          name: "Cùng nhau đi phượt (food tour Hải Phòng)",
          done: false
        },
        {
          name: "Cõng Xu đi 1 quãng đường",
          done: true
        },
        {
          name: "Để người lên đầu",
          done: true
        },
        {
          name: "Cùng nhau lên kế hoạch cho tương lai",
          done: false
        },
        {
          name: "Cùng nhau chơi trò tán tỉnh, một sẽ cố gắng tán tỉnh, một người sẽ khéo léo từ chối",
          done: false
        },
        {
          name: "Cùng nhau ngắm hoàng hôn và bình minh",
          done: false
        },
        {
          name: "Cùng nhau đón giao thừa và ngắm pháo hoa",
          done: false
        },
        {
          name: "Cùng nhau đi ăn xiên bẩn trước các cổng trường đại học",
          done: false
        },
        {
          name: "Cùng nhau đi kiểm tra sức khỏe",
          done: false
        },
        {
          name: "Cùng nhau vượt qua game co-op 2 người",
          done: true
        },
        {
          name: "Cùng nhau đi xe bus",
          done: true
        },
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
        // href: require("./assets/logo1.jpg")
      },
    ]
  },
  computed: {
    calculateLoverDate() {
      var currentDay = new Date();
      var loveDay = new Date("2023/09/02");
      // check year
      var countYear = Math.abs(currentDay.getFullYear() - loveDay.getFullYear());
      if (countYear > 1) {
        countYear = (countYear - 1) * 365;
      } else {
        countYear = 0;
      }
      console.log("countYear : " + countYear);
      // check month
      var countMonth = 0;
      if (currentDay.getMonth() < loveDay.getMonth()) {
        countMonth = ((12 + currentDay.getMonth()) - loveDay.getMonth()) * 30;
      } else {
        countMonth = Math.abs(currentDay.getMonth() - loveDay.getMonth()) * 30;
      }
      console.log("countMonth : " + countMonth);
      // check day
      var countDay = Math.abs(currentDay.getDate() - loveDay.getDate());
      console.log("countDay : " + countDay);
      return countYear + countMonth + countDay;
    },
    calculateDoneList() {
      var count = 0;
      this.todo.forEach((el) => {
        if (el.done) {
          count++;
        }
      })
      return count;
    },
    toDoListCount() {
      return this.todo.length
    }
  },
  methods: {
    onHoverPhoto(event, row = 0) {
      var element = event.target;
      var rect = element.getBoundingClientRect();
      var x = rect.left;
      var element_height = 512 * row;
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
@import url('@/assets/css/todo.css');

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


