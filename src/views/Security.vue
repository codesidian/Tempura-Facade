<template>

    <v-container fill-height>
<MainMenuButton/>

    <v-row align="center" justify="center">
      
      <v-col md="4">
<NavigationButton :buttonColour="'red'" :buttonText="'SENSORS'" :buttonLocation="'/Sensors'"/>      </v-col>

      <v-col md="4">
        <v-card elevation="0">
<NavigationButton :buttonColour="'darkred'" :buttonText="'MOTION'" :buttonLocation="'/Motion'"/>
        </v-card>
      </v-col>

      <v-col md="4">
<NavigationButton :buttonColour="'orange'" :buttonText="'CAMERAS'" :buttonLocation="'/Cameras'"/>      </v-col>

    </v-row>





    </v-container>

</template>

<script>
import NavigationButton from '@/components/NavigationButton';
import MainMenuButton from '@/components/MainMenuButton';

export default {
    name: 'Security',
    components: {
        NavigationButton,
        MainMenuButton
    },
    methods: {},
    data() {
        return {

        };
    },
};
</script>

<style>

</style>
