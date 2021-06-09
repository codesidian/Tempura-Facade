<template>
    <v-card tile outlined>
        <v-card-text :class="'sensor' + ' ' + triggeredCol" :id="sensor.id">
            Sensor #{{ sensor.id }} <v-spacer></v-spacer>

            <v-divider></v-divider>

            <v-card-title>
                {{ sensor.location }} <v-spacer></v-spacer>
                <span :class="availability.color">{{
                    availability.text
                }}</span></v-card-title
            >

            <v-card-subtitle>{{ sensor.type }}</v-card-subtitle>
            <v-divider></v-divider>

            <v-card-actions>
                <v-spacer></v-spacer>
                <div>Last Updated: {{ sensor.lastUpdated }} </div>
            </v-card-actions>
            
        </v-card-text>
    </v-card>
</template>

<script>
export default {
    name: 'SensorCard',
    props: ['sensor'],
    data() {
        return {
            sid: this.sensor.id,
            stype: this.sensor.type,
            slastUpdated: this.sensor.lastUpdated,
            sonline: this.sensor.online,
            striggered: this.sensor.triggered,
        };
    },

    computed: {

        availability() {
            let color = this.sensor.online ? 'green--text' : 'red--text';
            let text = this.sensor.online ? 'online' : 'offline';
            let online = {
                color: color,
                text: text,
            };
            return online;
        },
        triggeredCol() {
            let color = this.sensor.triggered ? 'triggered' : '';
            return color;
        },
    },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@100;500&display=swap');
.sensor {
    font-family: 'Raleway', sans-serif;
}

.triggered {
    -webkit-animation-duration: 1s;
    animation-duration: 1s;
    -webkit-animation-fill-mode: both;
    animation-fill-mode: both;
    animation-iteration-count: infinite;
    animation-name: flash;
}
.flash {
    animation-name: flash;
}
@keyframes flash {
    0%,
    50%,
    100% {
        background-color: rgb(255, 0, 0);
        color: white;
    }
    25%,
    75% {
        background-color: rgb(255, 255, 255);
        color: black;
    }
}
</style>
