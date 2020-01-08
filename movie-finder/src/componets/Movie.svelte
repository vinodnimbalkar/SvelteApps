<script>
  const DEFAULT_PLACEHOLDER_IMAGE =
    "https://m.media-amazon.com/images/M/MV5BMTczNTI2ODUwOF5BMl5BanBnXkFtZTcwMTU0NTIzMw@@._V1_SX300.jpg";

  export let movie;
  const poster = movie.Poster === 'N/A' ? DEFAULT_PLACEHOLDER_IMAGE : movie.Poster;
</script>

<style>
  .movie {
    padding: 5px 25px 10px 25px;
    max-width: 25%;
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

<div class="movie">
  <h2>{movie.Title}</h2>
  <div>
    <img
      src={poster}
      width="200px"
      alt={`The Movie Title : ${movie.Title}`} />
  </div>
  <p>({movie.Year})</p>
</div>
