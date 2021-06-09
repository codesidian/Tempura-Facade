<template>
    <v-row >
      <v-col md="12">
  <v-btn block color="green" @click="$router.go(-1)"> back </v-btn>

</v-col>
 </v-row >
</template>

<script>

export default {
    name: 'BackButton',
    components: {
        
    },
    methods:{
        goBack(){
            this.$router.go(-1); 
        }
    },
    props:{
    },
    data() {
        return {
        };
    },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@100;500&display=swap');
button {
    font-family: 'Raleway', sans-serif;
     min-height:75px;
     

}
</style>
