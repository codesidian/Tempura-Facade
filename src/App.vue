<template>
    <v-app>
        <v-content>
            <navigation></navigation>
            <router-view></router-view>
        </v-content>
    </v-app>
</template>
<script>
import Navigation from '@/components/Navigation';
import uniqueId from 'lodash.uniqueid';
//TODO: Refactor this crap (remove probably) to grab sensor data
//via API
let flex = 3;

export default {
    name: 'App',
    mounted(){
        this.$store.state.rooms = ['living room', 'gaming room', 'kitchen', 'bedroom'],
        this.$store.state.sensors = [
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Living Room',
                    lastUpdated: '17:30',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Living Room',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Living Room',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Living Room',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Gaming Room',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Gaming Room',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: true,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Gaming Room',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Kitchen',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Kitchen',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: true,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Kitchen',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Kitchen',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Bedroom',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Bedroom',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Motion',
                    location: 'Bedroom',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Motion',
                    location: 'Bedroom',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: true,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Motion',
                    location: 'Bedroom',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Animal Room',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Animal Room',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Mag Switch',
                    location: 'Animal Room',
                    lastUpdated: '17:31',
                    online: true,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Vibration Sensor',
                    location: 'Animal Room',
                    lastUpdated: '17:32',
                    online: false,
                    triggered: false,
                    flex: flex,
                },
                {
                    id: uniqueId(),
                    type: 'Vibration Sensor',
                    location: 'Animal Room',
                    lastUpdated: '17:33',
                    online: true,
                    triggered: true,
                    flex: flex,
                },
            ];
    },
    components: {
        Navigation,
    },
};
</script>
<style></style>
