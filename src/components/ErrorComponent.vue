<template>
    <v-sheet
        :color="`grey ${theme.isDark ? 'darken-2' : 'lighten-4'}`"
        class="px-3 pt-3 pb-3"
    >
        <v-skeleton-loader
            class="mx-auto"
            max-width="300"
            type="card"
        ></v-skeleton-loader>
    </v-sheet>
</template>

<script>
export default {
    name: 'ErrorComponent',
    data() {
        return {
            text: 'ERORR',
        };
    },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@100;500&display=swap');
.header {
    font-family: 'Raleway', sans-serif;
}
</style>
