<template>
<div>

          <svg-map style="" :map="customSchematic" 
                    :location-class="getLocationClass"
                    @mouseover="pointLocation"
                    @mouseout="unpointLocation"
                    @mousemove="moveOnLocation"
                    @focus="focusLocation"
                    @click="clickLocation"
          >

          </svg-map>
              <span class="tooltip" :style="tooltipStyle">{{ pointedLocation }}</span>

        <v-overlay
          :absolute="absolute"
          :value="overlay"
        >
        <h2>{{selectedOverlay}}</h2>
          <v-btn
            color="danger"
            @click="overlay = false"
          >
            Show Camera
          </v-btn>  
          <v-divider></v-divider>        
          <v-btn
            color="warning"
            @click="overlay = false"
          >
            Trigger Alert
          </v-btn>
          <v-divider></v-divider>
          <v-btn
            color="success"
            @click="overlay = false"
          >
            Close
          </v-btn>
        </v-overlay>

</div>
</template>

<script>

import { SvgMap } from "vue-svg-map";
import { getLocationName } from '../utilities'


export default {
    name: 'Motion',
    components: {
        SvgMap
    },
    props:{
      svgjson:[Object]
    },

    mounted(){
    },
    	methods: {
		pointLocation(event) {
			this.pointedLocation = getLocationName(event.target)
		},
		unpointLocation() {
			this.pointedLocation = null
			this.tooltipStyle = { display: 'none' }
		},
		moveOnLocation(event) {
			this.tooltipStyle = {
				display: 'block',
				top: `${event.clientY + 10}px`,
				left: `${event.clientX - 100}px`,
			}
    },
    clickLocation(event) {
      this.clickedLocation = getLocationName(event.target);
      this.overlay = !this.overlay;
      this.selectedOverlay = this.clickedLocation;
    },
    focusLocation(event) {
			this.focusedLocation = getLocationName(event.target)
		},
		getLocationClass(location) {
      let sensors = this.$store.state.sensors;
      let triggered = false;
      for (let i = 0; i < sensors.length; i++){
          if (location.name.toLowerCase() == sensors[i].location.toLowerCase() && 
              sensors[i].triggered){
                triggered = true;
          }
      }
      if (triggered){
        return `svg-map__location_TRIGGERED`
      }
      else{
        return `svg-map__location`
      }
		},
    },
    data() {
        return {
			customSchematic: {
				...this.svgjson,
				label: "Our House",
				locations: this.svgjson.location
      },
      pointedLocation: null,
      tooltipStyle: null,
      focusedLocation: null,      
      absolute: true,
      overlay: false,
      selectedOverlay: "",
        };
    },
};
</script>

<style>
.tooltip {
        display:none;
				position: fixed;
				width: 200px;
				padding: 10px;
				border: 1px solid darkgray;
				background-color: white;
			}

svg,
img {
  display: block;
  width:250px;

  height: auto;
}

path{
    stroke:black;
    stroke-width: 2px;
}
.svg-map__location{
fill:rgb(128, 128, 128);
}
.svg-map__location:hover{
  opacity: 0.75;
}

.svg-map__location_TRIGGERED{
fill:rgb(255, 0, 0);
}
</style>
