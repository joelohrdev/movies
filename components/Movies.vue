<template>
<div class="px-4 py-16 mx-auto sm:max-w-xl md:max-w-full lg:max-w-screen-xl md:px-24 lg:px-8 lg:py-20">
    <div class="grid gap-5 row-gap-5 mb-8 lg:grid-cols-4 sm:grid-cols-2">
        <router-link v-for="movie in movies" :to="{ name: 'movies-id', params: { id: movie.id }}" v-bind:key="movie.id" class="shadow-lg bg-gray-800 inline-block overflow-hidden duration-300 transform rounded shadow-sm hover:-translate-y-2">
            <div class="flex flex-col h-full">
                <img v-if="movie.favorite" class="fav" src="https://media.graphcms.com/rNiaYzLqRfmKY1KweOD2?_ga=2.135014900.402625854.1600903691-875593442.1600903691" alt="">
                <img :src="movie.coverImage.url" class="object-cover w-full h-60" alt="" />
                <div class="flex-grow rounded-b">
                    <div class="p-5">
                        <h6 class="font-semibold leading-4 text-gray-500 uppercase">{{ movie.title }}</h6>
                    </div>
                </div>
            </div>
        </router-link>
    </div>
</div>
</template>

<style>
.fav {
    width: 40px;
    position: absolute;
    top: 5px;
    right: 5px;
}
</style>

<script>
import moviesQuery from "~/apollo/queries/movies";
export default {
    data() {
        return {
            movies: [],
        };
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
