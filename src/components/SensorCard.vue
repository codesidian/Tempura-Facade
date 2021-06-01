<template>
<v-card>
    <v-card-text class="sensor" :id="id">
    <div >Sensor #{{ id }}</div>
    <p class="display-1 text--primary">
        Type: <span> {{type}} </span>
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
    prop: {
        id: {default: " asdasdasd", type: String},
        type: {default: " asdasdasd", type: String},
        lastUpdated: {default: " asdasdasd", type: String},
        online: {required: true, default: true, type: Boolean}
    },
    data() { 
        return {
                id: this.id,
                type: this.type,
                lastUpdated: this.lastUpdated,
                online: this.online
            };
    },
    computed: {
        availability() {
                let color = (!this.online) ? 'green--text' : 'red--text';
                let text = (!this.online) ? 'online' : 'offline';
                let online = {
                    "color":color,
                    "text":text
                }
                return online;
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
