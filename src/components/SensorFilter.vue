<template>
<span>
          <v-btn v-on:click="$emit('add-filter', 'living room')">Living Room</v-btn>
          <v-btn v-on:click="$emit('add-filter', 'bedroom')">Bedroom</v-btn>
          <v-btn v-on:click="$emit('add-filter', 'kitchen')">Kitchen</v-btn>
          <v-btn v-on:click="$emit('add-filter', 'gaming room')">Gaming Room</v-btn>
          <v-btn v-on:click="$emit('add-filter', 'animal room')">Animal Room</v-btn>
</span>
</template>

<script>
export default {
    name: 'SensorList',
    components: {
    },
    methods:{      

    },
    props:{},
    mounted(){
        console.log(this.filters)
    },
    data() {
        return {

        };
    },
};
</script>