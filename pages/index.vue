<template>
<div class="bg-gray-900">
    <div class="container h-screen">
        <Movies :movies="movies" />
    </div>
</div>
</template>

<script>
import moviesQuery from '~/apollo/queries/movies'
import Movies from '~/components/Movies'
export default {
    data() {
        return {
            movies: [],
        }
    },
    components: {
        Movies
    },
    apollo: {
        movies: {
            prefetch: true,
            query: moviesQuery,
            variables() {
                return {
                    id: parseInt(this.$route.params.id)
                }
            }
        }
    }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
    margin: 0 auto;
}

.title {
    font-family:
        'Quicksand',
        'Source Sans Pro',
        -apple-system,
        BlinkMacSystemFont,
        'Segoe UI',
        Roboto,
        'Helvetica Neue',
        Arial,
        sans-serif;
    display: block;
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
}

.subtitle {
    font-weight: 300;
    font-size: 42px;
    color: #526488;
    word-spacing: 5px;
    padding-bottom: 15px;
}

.links {
    padding-top: 15px;
}
</style>
