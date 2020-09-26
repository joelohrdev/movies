<template>
<div class="bg-gray-900">
    <div class="px-4 py-5 mx-auto sm:max-w-xl md:max-w-full lg:max-w-screen-xl md:px-24 lg:px-8">
        <div class="relative flex items-center justify-between">
            <nuxt-link to="/" aria-label="Movies" title="Movies" class="inline-flex items-center">
                <img class="h-5" src="https://media.graphcms.com/tniuSEbTRuua5FDqgEqn" />
            </nuxt-link>
        </div>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {
            isMenuOpen: false,
        };
    },
};
</script>
