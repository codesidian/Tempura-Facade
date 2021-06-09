<template>
    <v-container fluid>
        <SensorList :sensors="sensors" />
    </v-container>
</template>

<script>
import SensorList from '@/components/SensorList';

export default {
    name: 'Sensors',
    components: {
        SensorList,
    },
    methods: {},
    data() {
        return {
            sensors: this.$store.state.sensors
        };
    },
};
</script>

<style></style>
