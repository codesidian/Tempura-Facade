<template>
<v-container fill-height>
<BackButton/>
    <v-row align="center" justify="center">

      <v-col md="4">
      </v-col>
      <v-col md="4">
        <v-card elevation="0">
    <Schematic :svgjson="HS"  />
        </v-card>
      </v-col>
      <v-col md="4">
      </v-col>

    </v-row>





    </v-container>
</template> 

<script>
import Schematic from '@/components/Schematic';
import BackButton from '@/components/BackButton';
import jsonSVG from './jsonSVG.json'
var HouseSchematic = jsonSVG
export default {
    name: 'Motion',
    components: {
        Schematic,
        BackButton
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
