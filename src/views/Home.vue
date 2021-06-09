<template>

    <v-container fill-height>


    <v-row align="center" justify="center">
      
      <v-col md="4">
<NavigationButton :buttonColour="'error'" :buttonText="'SECURITY'" :buttonLocation="'/Security'"/>      </v-col>

      <v-col md="4">
        <v-card elevation="0">
<NavigationButton :buttonColour="'green'" :buttonText="'HOME'" :buttonLocation="'/'"/>
        </v-card>
      </v-col>

      <v-col md="4">
<NavigationButton :buttonColour="'warning'" :buttonText="'UTILITY'" :buttonLocation="'/Utility'"/>      </v-col>

    </v-row>





    </v-container>

</template>

<script>
import NavigationButton from '@/components/NavigationButton';

export default {
    name: 'Home',
    components: {
        NavigationButton
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
