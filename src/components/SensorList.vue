<template>
    <v-container fluid>
        <v-btn v-on:click="trigger()">trigger</v-btn>
        <v-btn v-on:click="untrigger()">untrigger</v-btn>
        <v-btn v-on:click="clearFilter()">All</v-btn>
        <SensorFilter :filters="rooms" v-on:add-filter="setFilter($event)" />
        <v-divider />

        <v-row dense>
            <v-col
                v-for="sensor in this.filteredList"
                :key="sensor.id"
                :cols="sensor.flex"
            >
                <SensorCard :sensor="sensor" />
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import SensorCard from '@/components/SensorCard';
import SensorFilter from '@/components/SensorFilter';

export default {
    name: 'SensorList',
    components: {
        SensorCard,
        SensorFilter,
    },
    methods: {
        trigger: function () {
            var i;
            var d = new Date();
            for (i = 0; i < this.sensors.length; i++) {
                this.sensors[i].triggered = true;
                this.sensors[i].lastUpdated =
                    d.getHours() + ':' + d.getMinutes();
            }
        },
        untrigger: function () {
            var i;
            var d = new Date();
            for (i = 0; i < this.sensors.length; i++) {
                this.sensors[i].triggered = false;
                this.sensors[i].lastUpdated =
                    d.getHours() + ':' + d.getMinutes();
            }
        },
        setFilter: function (filter) {
            this.filters = [];
            this.filters.push(filter);
            this.$forceUpdate();
        },
        clearFilter: function () {
            this.filters = [];
            this.$forceUpdate();
        },
    },
    computed: {
        filteredList() {
            var sensorlist;
            if (this.filters != '') {
                sensorlist = this.sensors.filter((sensor) =>
                    this.filters.includes(sensor.location.toLowerCase())
                );
            } else {
                sensorlist = this.sensors;
            }
            return sensorlist;
        },
    },
    //  TODO:     Prop needs to be refactored
    props: { sensors: [Array] },
    data() {
        return {
            rooms: ['living room', 'gaming room', 'kitchen', 'bedroom'],
            filters: [],
            
        };
    },
};
</script>

<style></style>
