<template>
        <v-item-group app color="blue-grey darken-3" class="sensor">

    <v-row>    
<SensorCard></SensorCard>
<SensorCard></SensorCard>
</v-row>
</v-item-group>
</template>

<script>
import SensorCard from '@/components/SensorCard';
export default {
    name: 'Home',
    components:{
        SensorCard,
    }
};
</script>

<style>

</style>
