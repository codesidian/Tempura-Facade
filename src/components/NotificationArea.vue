<template>

        <v-card  outline style="" :color="notificationData.colour" class="Notifcation-Area">
            {{notificationData.text}}
        </v-card>

</template>

<script>

export default {
    name: 'NotificationArea',
    components: {
        
    },
    methods:{

    },
    props:{
      
    },
    computed:{
        notificationData(){
            var data={
                text:'No Alerts',
                colour: 'white'
            };
            if (!this.$store.state.notifications){
                return data
            }
            else{
                return this.$store.state.notifications;
            }
            
        },
    },
    data() {
        return {
        };
    },
};
</script>

<style>

</style>
