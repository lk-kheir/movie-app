<script context="module">
    export async function load({fetch , params}) {
        const res = await fetch(`https://api.themoviedb.org/3/movie/${params.id}?api_key=27c689dd8b32b02b2db271915575bf32&language=en-US&page=1`)
        const movieDetail = await res.json();
        console.log(movieDetail)
        if (res.ok) {
            return {
                props: { movieDetail }
            }
        }
    }
</script>
<script>
    export let movieDetail;
    console.log(movieDetail)
</script>
<div class="movie-detail">
    <div class="img-container">
        <img
                src={'https://image.tmdb.org/t/p/original' + movieDetail.backdrop_path}
             alt={movieDetail.title}>

    </div>
    <div class="text-container">
        <h1>{movieDetail.title}</h1>
        <p>{movieDetail.overview}</p>
        <p>
            <span>released on: {movieDetail.release_date}</span>
            <br>
            <span>Average rating: {movieDetail.vote_average}</span>
        </p>
    </div>
</div>

<style>
    h1 {
        padding:1rem 0rem 2rem
    }
    p {
        padding: 1rem 0rem;
    }
    .img-container {
        width: 100%;
    }

    img {
        width: 100%;
    }

    .movie-detail {
        margin: 2rem 20%;
    }

    span {
        font-weight: bold ;
    }
</style>

