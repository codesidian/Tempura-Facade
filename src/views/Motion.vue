<template>
<v-container fluid>


    <v-row no-gutters>
      <v-col
        cols="12"
        sm="4"
      >
        <v-card
          class="pa-2"
          outlined
          tile
        >
    <Schematic :svgjson="HS" />
  
        </v-card>
      </v-col>
    </v-row>

    </v-container>
</template> 

<script>
import Schematic from '@/components/Schematic';
import jsonSVG from './jsonSVG.json'
var HouseSchematic = jsonSVG
export default {
    name: 'Motion',
    components: {
        Schematic
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
