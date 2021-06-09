<template>
    <v-app-bar app color="blue-grey darken-3" dark class="header">
        <v-spacer/>
        <v-icon inline left>mdi-eye</v-icon>
        <v-toolbar-title> {{ appTitle }}</v-toolbar-title>
        <v-spacer/>
    </v-app-bar>
</template>

<script>
export default {
    name: 'Navigation',
    data() {
        return {
            appTitle: 'TEMPURA',
            items: [
                { title: 'Home', to: "/" },
                { title: 'Security', to: "/Security" },
            ],
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
