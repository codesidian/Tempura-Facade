<template>
        <v-app-bar app color="blue-grey darken-3" dark class="header">
            <v-icon inline left>mdi-eye</v-icon> 
            <v-toolbar-title >{{appTitle}}</v-toolbar-title>

            <v-spacer></v-spacer>
            <template v-for="(item, index) in items">
                    <v-btn :key="index" text>{{item.title}}</v-btn>
            </template>

            <v-btn color="blue-grey darken-1" >REFRESH</v-btn>
        </v-app-bar>
</template>

<script>

export default {
    name: 'Navigation',
    data() { 
        return {
                appTitle: 'TEMPURA',
                items: [
                    { title: 'Camera' },
                    { title: 'Motion' },
                    { title: 'Windows & Doors' }
                ],
            };
    }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@100;500&display=swap');
.header{
    font-family: 'Raleway', sans-serif;
}
</style>
