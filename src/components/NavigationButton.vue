<template>
  <v-btn block :color="buttonColour" :to="buttonLocation"> {{buttonText}} </v-btn>
</template>

<script>
export default {
    name: 'NavigationButton',
    props:{
      buttonText:[String],
      buttonLocation:[String],
      buttonColour:[String]
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
     min-height:250px;

}
</style>
