<script>
  import Header from "./componets/Header.svelte";
  import Movie from "./componets/Movie.svelte";
  import Search from "./componets/Search.svelte";

  const MOVIE_API_URL = "https://www.omdbapi.com/?s=Avengers&apikey=4a3b711b";

  let loading = true;
  let movies = "";
  let errorMessage = null;

  const fetchMovie = async () => {
    const respose = await fetch(MOVIE_API_URL);
    const jsonResposnse = await respose.json();
    movies = jsonResposnse.Search;
    loading = false;
  };

  fetchMovie();

  const search = async searchValue => {
    loading = true;
    errorMessage = null;

    const respose = await fetch(
      `https://www.omdbapi.com/?s=${searchValue}&apikey=4a3b711b`
    );
    const jsonResponse = await respose.json();
    if (jsonResponse.Response === "True") {
      movies = jsonResponse.Search;
      loading = false;
    } else {
      errorMessage = jsonResponse.Error;
      loading = false;
    }
  };
</script>

<style>
  .App {
    text-align: center;
  }

  .App-intro {
    font-size: large;
  }
  * {
    box-sizing: border-box;
  }
  .movies {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
  }
  .errorMessage {
    margin: auto;
    font-weight: bold;
    color: rgb(161, 15, 15);
  }
</style>

<div class="App">
  <Header text={'Movie Finder'} />
  <Search {search} />
  <p class="App-intro">Sharing a few of our Movies</p>
  <div class="movies container">
    {#if loading && !errorMessage}
      <span>loading ...</span>
    {:else if errorMessage}
      <div class="errorMessage">{errorMessage}</div>
    {:else}
      {#each movies as movie}
        <Movie {movie} />
      {/each}
    {/if}
  </div>
</div>
