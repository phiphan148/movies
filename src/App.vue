<template>
  <Header></Header>
</template>

<script>
import Header from "./components/Header";
export default {
  name: 'App',
  components: {Header},
  data () {
    return {
      series: [],
      movie: [],
      hottrend: [],
      episode: [],
      noneType: []
    }
  },
  created() {
    this.getMovieData();
  },
  methods: {
    getMovieData() {
        fetch('https://api.myjson.com/bins/15mzg8')
          .then(response => response.json())
          .then(jsondata => {
            let data = jsondata.movies;
            console.log(data);
            data.forEach(movie => {
              switch (movie.Type) {
                case "series":
                  this.series.push(movie);
                  break;
                case "movie":
                  this.movie.push(movie);
                  break;
                case "episode":
                  this.episode.push(movie);
                  break;
                default:
                  this.noneType.push(movie);
              }
            })
            console.log(this.series);
            console.log(this.movie);
            console.log(this.episode);
            console.log(this.noneType);
          })

    }
  }
}
</script>

<style>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
