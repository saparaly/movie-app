<template>
    <div class="space"></div>
    <section class="movie">
        <div class="container">
            <div class="movie__container">
                <h1 class="title">{{ movie.Title }}</h1>
                <div class="movie__header">
                    <div class="movie__date">
                        <span>Year: {{ movie.Year }}</span>
                        <span>Released: {{ movie.Released }}</span>
                        <span>Runtime: {{ movie.Runtime }}</span>
                    </div>
                    <span>Genre: {{ movie.Genre }}</span>
                </div>
                <div class="box">
                    <div class="img">
                        <img :src="movie.Poster" alt="">
                    </div>
                    <div class="content">
                        <p>{{ movie.Plot }}</p>
                        <div class="content__box">
                            <p>Awards: {{ movie.Awards }}</p>
                            <p>Country: {{ movie.Country }}</p>
                            <p>Language: {{ movie.Language }}</p>
                            <p>Director: {{ movie.Director }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        id: null,
        movie: null,
      };
    },
    created() {
        this.id = this.$route.params.id;
        this.fetchMovieDetails().catch(error => console.log(error));
    },
    methods: {
        async fetchMovieDetails() {
            const apiKey = "f140b96e";
            const url = `http://www.omdbapi.com/?apikey=${apiKey}&i=${this.id}`;
            const response = await fetch(url);
            const data = await response.json();
            this.movie = data;
            console.log(data)
        }
    },
  };
  </script>

<style scoped>
.space{
    margin-top: 150px;
}

.title {
    margin-bottom: 0px;
}
.movie__header{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 50px;
    font-weight: 600;
    font-size: 20px;

    color: #E64E9A;
}
.movie__date{
    display: flex;
    align-items: center;
    gap: 30px;
}
.box {
    display: flex;
}
.content {
    margin-left: 50px;
}
.content__box {
    margin-top: 50px;
}
.content__box p {
    margin-bottom: 10px;
}
</style>