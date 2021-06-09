<template>

    <v-container fill-height>
      <BackButton/>

      <div  class="header">
        <h1>Security</h1>
      </div>

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
import BackButton from '@/components/BackButton';
export default {
    name: 'Security',
    components: {
        NavigationButton,
        BackButton
    },
    methods: {},
    data() {
        return {

        };
    },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@100;500&display=swap');

.header{
  font-family: 'Raleway', sans-serif;
  text-align:center;
  margin:auto;

}
</style>
