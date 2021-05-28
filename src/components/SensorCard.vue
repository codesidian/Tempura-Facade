<template>
<v-card>
    <v-card-text class="sensor">
    <div>Sensor #{{properties.id}}</div>
    <p class="display-1 text--primary">
        Type: <span > {{properties.type}} </span>
    </p>
    <p class="display-1 text--primary">
        Status: <span :class="availability.color" > {{availability.text}} </span>
    </p>

    
        Last Updated: {{lastUpdated}}     
    </v-card-text>
</v-card>
</template>

<script>

export default {
    name: 'SensorCard',
    data() { 
        return {
                properties: {
                    id: 0,
                    type: "Door Mag"
                },
                lastUpdated: "17:32",
                status: {availability: true,}
            };
    },
    computed: {
        availability() {
                let color = (!status.availability) ? 'green--text' : 'red--text';
                let text = (!status.availability) ? 'online' : 'offline';
                let availability = {
                    "color":color,
                    "text":text
                }
                return availability;
        }
    }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@100;500&display=swap');
.sensor{
    font-family: 'Raleway', sans-serif;
}

</style>
