<template>

    <v-container fill-height>
      <BackButton />

      <div  class="header">
        <h1>Our Home</h1>
      </div>

    <v-row align="center" justify="center">
      
      <v-col md="4">
 </v-col>
      <v-col md="4">
 </v-col>

      <v-col md="4">
 </v-col>

  </v-row>





    </v-container>

</template>

<script>
import BackButton from '@/components/BackButton';
export default {
    name: 'OurHome',
    components: {
        BackButton
    },
    methods: {},
    data() {
        return {

        };
    },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@100;500&display=swap');

.header{
  font-family: 'Raleway', sans-serif;
  text-align:center;
  margin:auto;

}
</style>
