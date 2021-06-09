<template>
<v-container fluid>
<MainMenuButton/>

    <v-row >
      
      <v-col md="2">
        
      </v-col>

      <v-col md="10">
        <v-card elevation="0">
    <Schematic :svgjson="HS"  />
        </v-card>
      </v-col>


    </v-row>





    </v-container>
</template> 

<script>
import Schematic from '@/components/Schematic';
import MainMenuButton from '@/components/MainMenuButton';
import jsonSVG from './jsonSVG.json'
var HouseSchematic = jsonSVG
export default {
    name: 'Motion',
    components: {
        Schematic,
        MainMenuButton
    },

    mounted(){
      
    },
    methods: {

    },
    computed:{
 
    },
    data() {
        return {
          HS: HouseSchematic
        };
    },
};
</script>

<style>

</style>
