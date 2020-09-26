<template>
<div>
    <h1 v-if="movie.title">test</h1>
    <p>{{ movie.title }}</p>
    {{ movie.id }}
    <p>test</p>
</div>
</template>

<script>
import movieQuery from "~/apollo/queries/movie"
export default {
    data() {
        return {
            movie: {},
        }
    },
    apollo: {
        movie: {
            prefetch: true,
            query: movieQuery,
        }
    }
}
</script>
