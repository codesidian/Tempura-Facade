<template>
    <v-app>
        <v-content>
            <navigation></navigation>
            <router-view></router-view>
        </v-content>
    </v-app>
</template>
<script>
import Navigation from '@/components/Navigation';
export default {
    name: 'App',
    components: {
        Navigation,
    },
};
</script>
<style></style>
