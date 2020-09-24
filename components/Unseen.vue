<template>
  <div class="px-4 py-16 mx-auto sm:max-w-xl md:max-w-full lg:max-w-screen-xl md:px-24 lg:px-8 lg:py-20">
    <div class="grid gap-5 row-gap-5 mb-8 lg:grid-cols-6 sm:grid-cols-2">
      <a v-for="movie in movies" v-bind:key="movie.id" href="/" aria-label="View Item" class="inline-block overflow-hidden duration-300 transform bg-white rounded hover:-translate-y-2">
        <div class="flex flex-col h-full">
          <img :src="movie.coverImage.url" class="object-cover w-full h-60" alt="" />
          <div class="flex-grow rounded-b">
            <div class="py-3">
              <h6 class="font-semibold leading-5">{{ movie.title }}</h6>
              <!-- <p class="text-sm text-gray-500">
                {{ movie.releaseDate }}
              </p> -->
            </div>
          </div>
        </div>
      </a>
    </div>
  </div>
</template>

<script>
import moviesQuery from "~/apollo/queries/unseenMovies";
export default {
    data() {
        return {
            movies: [],
        };
    },
    apollo: {
        movies: {
            prefetch: true,
            query: moviesQuery
        }
    }
}
</script>