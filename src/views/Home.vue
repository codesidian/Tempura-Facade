<template>
    <v-item-group app color="blue-grey darken-3" class="sensor">
        <div v-for="sensor in sensors" :key="sensor.id">
        <SensorCard id="sensor.id" type="sensor.type" lastUpdated="sensor.lastUpdated" online="sensor.online"/>
        </div>
    </v-item-group>
</template>

<script>
import SensorCard from '@/components/SensorCard';
import uniqueId from 'lodash.uniqueid';

export default {


    name: 'Home', 
    components:{
        SensorCard,
    },
  data() {
    return {
      sensors: [
        { id: uniqueId(), type: 'test0', lastUpdated: '17:30', online: true },
        { id: uniqueId(), type: 'test1', lastUpdated: '17:31', online: true },
        { id: uniqueId(), type: 'test2', lastUpdated: '17:32', online: true },
        { id: uniqueId(), type: 'test3', lastUpdated: '17:33', online: true }
      ]
    };
  }

};
</script>

<style>

</style>
