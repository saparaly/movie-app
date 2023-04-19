<template>
  <section class="banner">
    <div class="swiper-container height ">
      <div class="swiper-wrapper">
        <div v-for="(slide, index) in slides" :key="index" class="swiper-slide">
          <img :src="slide.imageUrl" alt="" class="banner__img">
          <div class="container">
            <div class="banner__container">
              <div class="banner__container-content">
                <ul>
                  <li>9.00</li>
                  <li>ПРОДОЛЖИТЕЛЬНОСТЬ</li>
                </ul>
                <h2>{{ slide.title }}</h2>
                <p>Члены дома Таргариенов оставляют обреченную Валирию и отправляются на запад, где обнаруживают огромную территорию, населенную враждующими королевствами.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>
    </div>
  </section>
</template>
  
  <script>
  import Swiper from 'swiper'
//   import 'swiper/css/swiper.css'
  
  export default {
    data() {
      return {
        slides: [
          {
            imageUrl: 'https://wallpapers.com/images/featured/plzcoaffexgf4h81.jpg',
            title: 'ДОМ ДРАКОНА'
          },
          {
            imageUrl: 'https://images4.alphacoders.com/814/81446.jpg',
            title: 'ВЕРНУТЬ ВРЕМЯ'
          },
          {
            imageUrl: 'https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/1b9a551a-0102-4cbd-91d0-292a58acd680/depv42q-72095a28-9ac6-4c4d-b4ad-42623f4c8ac3.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzFiOWE1NTFhLTAxMDItNGNiZC05MWQwLTI5MmE1OGFjZDY4MFwvZGVwdjQycS03MjA5NWEyOC05YWM2LTRjNGQtYjRhZC00MjYyM2Y0YzhhYzMuanBnIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.yKRu05XAQVziHmwT4Sm0olnvFITaNvPfcwY_ZGYkKgk',
            title: 'ЗАКАТ ЧЕЛОВЕЧЕСТВА'
          }
        ]
      }
    },
    mounted() {
      new Swiper('.swiper-container', {
        loop: true,
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        },
        navigation: {
          prevEl: '.swiper-button-prev',
          nextEl: '.swiper-button-next'
        },
      })
    }
}

</script>


<style scoped>
section{
  padding: 0;
}
.swiper-button-prev, .swiper-button-next{
  z-index: 100;
}
.banner {
  overflow: hidden;
  height: 60vh;
  width: 100%;
  position: relative;
}

.banner__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  position: absolute;
}
.height {
  width: 100%;
  height: 100%;
  position: relative;
}
.swiper-slide {
  position: relative;
}
.swiper-slide::before {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(180deg, rgba(0, 0, 0, 0) 0%, #000000 84.7%);
  z-index: 1;
}
.swiper-slide::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 138px;
  z-index: 1;
  background: linear-gradient(180deg, rgba(0, 0, 0, 0) 0%, #000000 84.7%);
  transform: matrix(1, 0, 0, -1, 0, 0);
}
.banner .container {
  height: 100%;
}
.banner__container{
  width: 100%;
  height: 100%;
  position: relative;
  z-index: 2;
  width: 608px;
  font-weight: 400;
font-size: 17px;
}

.banner__container-content {
  position: absolute;
  top: 30%;
  left: 0;
}

h2{
  font-weight: 800;
font-size: 72px;
letter-spacing: -0.03em;
color: #FFFFFF;
}
</style>
   
  