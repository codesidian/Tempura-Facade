<template>

    <v-container fill-height>

    <v-row >
      
      <v-col md="12">
            <NotificationArea/>
     </v-col>


    </v-row>


    <v-row align="center" justify="center">
      
      <v-col md="4">
<NavigationButton :buttonColour="'error'" :buttonText="'SECURITY'" :buttonLocation="'/Security'"/>      </v-col>

      <v-col md="4">
        <v-card elevation="0">
<NavigationButton :buttonColour="'green'" :buttonText="'our home'" :buttonLocation="'/OurHome'"/>
        </v-card>
      </v-col>

      <v-col md="4">
<NavigationButton :buttonColour="'warning'" :buttonText="'UTILITY'" :buttonLocation="'/Utility'"/>      </v-col>

    </v-row>





    </v-container>

</template>

<script>
import NavigationButton from '@/components/NavigationButton';
import NotificationArea from '@/components/NotificationArea';

export default {
    name: 'Home',
    components: {
        NavigationButton,
        NotificationArea
    },
    methods: {},
    data() {
        return {

        };
    },
};
</script>

<style>
.Notifcation-Area{
padding:25px;
text-align:center;

}
</style>
