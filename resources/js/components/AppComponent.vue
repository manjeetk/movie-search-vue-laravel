<template>
  <div class="text-center mt-3 border rounded">
    <Header :title="'Search for a Movie'" />
    <Search :search="state.search" @search="handleSearch" />
    <div class="movies m-5">
      <Movie v-for="movie in state.movies" :movie="movie" :key="movie.imdbID" />
    </div>
  </div>
</template>

<script>
import Header from './HeaderComponent.vue';
import Search from './SearchComponent.vue';
import Movie from './MovieComponent.vue';
import { useMovieApi } from '../movieapi/movie-api';

export default {
    name: 'app',
    components: { Header, Search, Movie },
    setup() {
        const state = useMovieApi();
        return {
            state,
            handleSearch(searchTerm) {
                state.loading = true;
                state.search = searchTerm;
            }
        };
    }
}
</script>

<style>

* {
    box-sizing: border-box;
}

.header {
    background-color: #165365;
    height: 3em;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    font-size: calc(10px + 2vmin);
    color: white;
    padding: 20px;
    cursor: pointer;
    border-radius: 5px;
}

.movies {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
}

.movie {
    padding: 5px 25px 5px 25px;
    max-width: 25%;
}

.search {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 20px;
}

h2 {
    font-size: 22px;
}
input[type="submit"] {
    padding: 5px;
    background-color: #ee372c;
    color: #fff;
    border: 1px solid #ee372c;
    border-radius: 10px;
    width: 80px;
    margin-left: 5px;
    cursor: pointer;
}

input[type="submit"]:hover {
    background-color: #165365;
    border: 1px solid #165365;
    border-radius: 10px;
    color: #fff;
}

.search > input[type="text"]{
    width: 40%;
    min-width: 170px;
}

@media screen and (min-width: 694px) and (max-width: 915px) {
    .movie {
        max-width: 33%;
    }
}

@media screen and (min-width: 652px) and (max-width: 693px) {
    .movie {
        max-width: 50%;
    }
}

@media screen and (max-width: 651px) {
    .movie {
        max-width: 100%;
        margin: auto;
    }
}
</style>
