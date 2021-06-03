<template>
    <v-container fluid>
        <SensorList :sensors="sensors" />
    </v-container>
</template>

<script>
import SensorList from '@/components/SensorList';

export default {
    name: 'Home',
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
