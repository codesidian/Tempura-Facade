<template>
    <v-row >
      <v-col md="12">
<NavigationButton :buttonColour="'green'" :buttonText="'BACK'" @click="goBack()"/>      
</v-col>
 </v-row >
</template>

<script>
import NavigationButton from '@/components/NavigationButton';

export default {
    name: 'MainMenuButton',
    components: {
        NavigationButton
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
a {
    font-family: 'Raleway', sans-serif;
     min-height:150px;
     

}
</style>
