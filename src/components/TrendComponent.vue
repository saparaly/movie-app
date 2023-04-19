<template>
    <section class="popular">
        <div class="container">
            <h3 class="title">В тренде</h3>
            <div class="popular__header">
                <ul class="popular__header-left">
                    <li>Все:</li>
                    <li>Экшен:</li>
                    <li>Фантастика:</li>
                    <li>Приключения</li>
                </ul>
                <div class="popular__header-right">смотреть все</div>
            </div>
            <div class="popular__container">
                <RouterLink :to="{ name: 'movie', params: { id: item.imdbID } }" 
                class="popular__item" 
                v-for="item in movie.Search" :key="item.imdbID">
                    <img :src="item.Poster" alt="">
                    <div class="type">
                        <p>{{ item.Type }}</p>
                        <div class="bg"></div>
                    </div>
                    <div class="text">
                        <div class="block">
                            <span>IMDb</span>
                            <div class="id">{{ item.imdbID }}</div>
                        </div>
                        <p>{{ item.Year }}</p>
                        <h4>{{ item.Title }}</h4>
                    </div>
                </RouterLink>
            </div>
        </div>
    </section>
</template>

<script>
import axios from 'axios'

export default {
    data() {
    return{
      movie: {},
    }
  },
  created() {
    axios
      .get('http://www.omdbapi.com/?apikey=f140b96e&s=star+wars')
      .then(response => {
        (this.movie = response.data)
        // console.log(response.data)
      })
      .catch(error => console.log(error))
  }
}
</script>

<style scoped>
section{
    background: #131315;
}
.popular__header {
    margin-bottom: 50px;
}
.popular__header, .popular__header-left {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.popular__header-left li{
    margin-right: 40px;
    font-weight: 800;
    font-size: 13px;
    text-transform: uppercase;
    color: #E64E9A;
}

.popular__container {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-auto-rows: 344px;
    grid-gap: 17px;
    grid-row-gap: 24px;
}

.popular__item {
    position: relative;
}
.popular__item::before{
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(180deg, rgba(0, 0, 0, 0) 0%, #000000 100%), url(image.png);
    z-index: 1;
}
.popular__item img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.text{
    position: absolute;
    bottom: 30px;
    left: 20px;
    z-index: 2;
}
.text h4 {
    font-weight: 800;
    font-size: 18.4531px;
}
.text p{
    font-weight: 500;
    font-size: 13px;
}
.text span {
    font-weight: 800;
    font-size: 13px;
    color: #020102;
    background: #F6D838;
    border-radius: 2px;
    padding: 4px;
    display: block;
    width: fit-content;
}

.block {
    display: flex;
    align-items: center;
    margin-bottom: 12px;
}
.block .id {
    font-weight: 800;
    font-size: 14px;
    margin-left: 12px;
}
.type {
    position: absolute;
    left: 0;
    top: 20px;
    padding: 10px 20px;
    width: fit-content;
    height: fit-content;
    font-weight: 500;
    font-size: 13px;
    z-index: 20;
}
.bg{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #000000;
    opacity: 0.75;
    z-index: 10;
}
.type p {
    z-index: 20;
}
</style>